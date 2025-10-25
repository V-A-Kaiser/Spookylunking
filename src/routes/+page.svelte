<script lang="ts">
  import '../app.css';
  import favicon from '$lib/assets/icon.png';
  import video from '$lib/assets/websitebackground.webm';
  import scores from '$lib/scores.json';
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
  <title>Spookylunking</title>
</svelte:head>

<!-- Background Video -->
<video
  src={video}
  autoplay
  muted
  loop
  playsinline
  disablepictureinpicture
  disableremoteplayback
  class="fixed inset-0 z-[-1] h-full w-full object-cover select-none"
/>

<header class="flex items-center justify-center p-4">
  <h1
    class="font-cormorant text-[8vw] leading-none font-thin tracking-wide text-white uppercase text-shadow-lg/90 md:text-6xl"
  >
    Spookylunking
  </h1>
</header>

<main class="grid grid-cols-2 gap-4 p-8 md:grid-cols-3 lg:grid-cols-4">
  {#each scores as score}
    <div class="flex cursor-pointer flex-col items-center hover:scale-105 transition-all duration-300">
      <!-- Video Thumbnail -->
      <img
        src={`https://img.youtube.com/vi/${score.video.substring(17)}/maxresdefault.jpg`}
        alt={score.title}
        class="h-auto w-full rounded-lg"
      />
      <h2
        class="my-4 text-center font-cormorant text-2xl leading-none font-thin tracking-wide text-white text-shadow-lg/90"
      >
        {score.title}
      </h2>
    </div>
  {/each}
</main>
