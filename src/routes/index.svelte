<script context="module"></script>
<script>
  import detectIE from '../components/helpers/detectIE.js';
  const isIE = detectIE();
</script>

{#if isIE} {#await import('../components/fragments/noIE.svelte') then c}
<svelte:component this="{c.default}"></svelte:component>
{/await} {/if}

<main></main>

<style global>
  :root {
    /* colors */
    --wine: #842612;
    --ocher: #d4ca6e;
    --cream: #f5f4ee;
    --shadow: rgba(0, 0, 0, 0.2);
    --d-shadow: rgba(0, 0, 0, 0.3);
    /* fonts */
    --noto: 'Noto Sans', Roboto, sans-serif;
    --gothic: YuGothic, '游ゴシック体', 'Yu Gothic', Roboto, sans-serif;
    --times: 'Times New Roman', Times, serif;
    /* others */
    --skl: 7deg;
    --skr: -4deg;
    scroll-behavior: smooth;
  }
  body {
    font-family: var(--gothic);
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  main {
    overflow: hidden;
  }
  section:focus {
    outline: none;
  }
  .d-shadow {
    filter: drop-shadow(5px 5px 3px var(--shadow));
  }
  .d-shadow-light {
    filter: drop-shadow(0px 3px 5px var(--d-shadow));
  }
  .abs {
    position: absolute;
  }

  .skl,
  .skr {
    transition: transform 0.2s;
  }
  .skl:hover {
    transform: skew(var(--skl)) scale(1.04);
  }
  .skr:hover {
    transform: skew(var(--skr)) scale(1.01);
  }
</style>
