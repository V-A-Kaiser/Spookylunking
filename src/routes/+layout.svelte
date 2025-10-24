<script lang="ts">
  import '../app.css';
  import favicon from '$lib/assets/icon.png';
  import video from '$lib/assets/websitebackground.webm';

  let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
  <title>Spookylunking</title>
</svelte:head>

<!-- Background Video -->
<video src={video} autoplay muted loop playsinline disablepictureinpicture disableremoteplayback class="absolute inset-0 z-[-1] w-full h-full object-cover"/>

<header class="flex justify-center items-center p-4">
  <h1 class="font-cormorant leading-none text-[8vw] md:text-6xl font-thin uppercase text-white text-shadow-lg/90 tracking-wide">Spookylunking</h1>
</header>

<main>
  {@render children?.()}
</main>
