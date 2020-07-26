<script context="module">
  export async function preload(page, session) {
    const fs = require('fs').promises;
    const files = await fs.readdir('static/deites');
    const imgPaths = files.map((file) => `deites/${file}`);
    return { imgPaths };
  }
</script>

<script>
  import Slide from '../components/Slide.svelte';
  import Slider from '../components/Slider.svelte';
  export let imgPaths;
</script>

<style>
  .img {
    width: 100%;
    height: 100%;
  }
</style>

<svelte:head>
  <title>Darshan</title>
</svelte:head>

<main class="page">
  <Slider>
    {#each imgPaths as src}
      <Slide>
        <div class="img" style={`background: url("${src}") center center / contain no-repeat`}></div>
      </Slide>
    {/each}
  </Slider>
</main>
