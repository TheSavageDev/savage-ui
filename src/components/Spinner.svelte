<script>
  import { onMount } from 'svelte';
  import { omit } from '../lib/utils';

  export let size = 'medium';

  const sizeOpts = ['tiny', 'small', 'medium', 'large', 'huge', 'enormous', 'gigantic', 'stupid'];
  
  if (!sizeOpts.includes(size)) {
    size = 'medium';
  }

  $: props = {
    ...omit(
      $$props,
    ),
    class: `spinner ${size} ${$$props.class || ""}`,
  }
</script>

<style>
  article,
  article:after {
    border-radius: 50%;
  }
  article {
    font-size: 10px;
    position: relative;
    text-indent: -9999em;
    border-top: 0.5rem solid var(--dark-accent);
    border-right: 0.5rem solid var(--brand);
    border-bottom: 0.5rem solid var(--dark-accent);
    border-left: 0.5rem solid var(--brand);
    transform: translateZ(0);
    animation: spin 1.1s infinite linear;
  }

  .tiny {
    height: 0.125rem;
    width: 0.125rem;
  }

  .small {
    height: 2rem;
    width: 2rem;
  }

  .medium {
    height: 5rem;
    width: 5rem;
  }
  
  .large {
    height: 8rem;
    width: 8rem;
  }
  .huge {
    height: 11rem;
    width: 11rem;
  }
  .enormous {
    height: 15rem;
    width: 15rem;
  }
  .gigantic {
    height: 20rem;
    width: 20rem;
  }
  .stupid {
    height: 50rem;
    width: 50rem;
  }
  @-webkit-keyframes spin {
    0% {
      -webkit-transform: rotate(0deg);
      transform: rotate(0deg);
    }
    100% {
      -webkit-transform: rotate(360deg);
      transform: rotate(360deg);
    }
  }
  @keyframes spin {
    0% {
      -webkit-transform: rotate(0deg);
      transform: rotate(0deg);
    }
    100% {
      -webkit-transform: rotate(360deg);
      transform: rotate(360deg);
    }
  }
</style>

<article {...props} />
