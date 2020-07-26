<script>
  import { onMount } from 'svelte';

  onMount(async () => {
    const module = await import('@splidejs/splide');
    const Splide = module.default;
    const options = {
      type: 'loop',
      perPage: 1,
      // cover: true,
      gap: '1em',
      height: '100vh',
      // fixedHeight: '20rem',
      // autoWidth: true,
      width: '100vw',
      // heightRatio: '0.7',
    }
    new Splide('.splide', options).mount();
  });
</script>

<div class="splide">
  <div class="splide__track">
    <ul class="splide__list">
      <slot />
    </ul>
  </div>
</div>
