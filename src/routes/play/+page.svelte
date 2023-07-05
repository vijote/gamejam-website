<script lang="ts">

    import { onMount, onDestroy } from "svelte";

    let unityInstanceRef: unknown;

    onMount(() => {
        const container = document.querySelector(
            "#unity-container"
        ) as HTMLElement;
        const canvas = document.querySelector(
            "#unity-canvas"
        ) as HTMLCanvasElement;
        const loadingBar = document.querySelector(
            "#unity-loading-bar"
        ) as HTMLElement;
        const progressBarFull = document.querySelector(
            "#unity-progress-bar-full"
        ) as HTMLElement;
        const fullscreenButton = document.querySelector(
            "#unity-fullscreen-button"
        ) as HTMLElement;
        const warningBanner = document.querySelector(
            "#unity-warning"
        ) as HTMLElement;

        function unityShowBanner(msg: string, type: string) {
            function updateBannerVisibility() {
                warningBanner.style.display = warningBanner.children.length
                    ? "block"
                    : "none";
            }

            const div = document.createElement("div");
            div.innerHTML = msg;
            warningBanner.appendChild(div);

            if (type == "error") {
                div.style.background = "red";
                div.style.padding = "10px";
            } else {
                if (type == "warning") {
                    div.style.background = "yellow";
                    div.style.padding = "10px";
                }

                setTimeout(() => {
                    warningBanner.removeChild(div);
                    updateBannerVisibility();
                }, 5000);
            }

            updateBannerVisibility();
        }

        const loaderUrl = `/jadev-jam-web.loader.js`;
        const config = {
            dataUrl: `/jadev-jam-web.data.gz`,
            frameworkUrl: `/jadev-jam-web.framework.js.gz`,
            codeUrl: `/jadev-jam-web.wasm.gz`,
            streamingAssetsUrl: "StreamingAssets",
            companyName: "DefaultCompany",
            productName: "JadevJam",
            productVersion: "0.1",
            showBanner: unityShowBanner,
        };

        if (/iPhone|iPad|iPod|Android/i.test(navigator.userAgent)) {
            const meta = document.createElement("meta");
            meta.name = "viewport";
            meta.content =
                "width=device-width, height=device-height, initial-scale=1.0, user-scalable=no, shrink-to-fit=yes";
            document.getElementsByTagName("head")[0].appendChild(meta);
            container.className = "unity-mobile";
            canvas.className = "unity-mobile";
        } else {
            canvas.style.width = "960px";
            canvas.style.height = "600px";
        }

        loadingBar.style.display = "block";

        const script = document.createElement("script");
        script.src = loaderUrl;
        script.onload = () => {
            createUnityInstance(canvas, config, (progress: number) => {
                progressBarFull.style.width = `${100 * progress}%`;
            })
                .then((unityInstance) => {
                    unityInstanceRef = unityInstance;
                    loadingBar.style.display = "none";
                    fullscreenButton.onclick = () => {
                        unityInstance.SetFullscreen(1);
                    };
                })
                .catch((message: any) => {
                    alert(message);
                });
        };

        document.body.appendChild(script);
    });

    onDestroy(() => {
        unityInstanceRef.Quit();
    })
</script>

<svelte:head>
    <title>Jugar | El ascenso del Depredador</title>
</svelte:head>

<div id="unity-container" class="unity-desktop">
    <canvas id="unity-canvas" width="960" height="600" tabindex="-1" />
    <div id="unity-loading-bar">
        <div id="unity-logo" />
        <div id="unity-progress-bar-empty">
            <div id="unity-progress-bar-full" />
        </div>
    </div>
    <div id="unity-warning" />
    <div id="unity-footer">
        <div id="unity-webgl-logo" />
        <div id="unity-fullscreen-button" />
        <div id="unity-build-title">JadevJam</div>
    </div>
</div>
