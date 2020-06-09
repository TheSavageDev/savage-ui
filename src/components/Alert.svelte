<script>
  import { slide, fly } from 'svelte/transition';
  import Information from "svelte-material-icons/Information.svelte";
  import Alert from "svelte-material-icons/Alert.svelte";
  import ThumbUp from "svelte-material-icons/ThumbUp.svelte";
  import MinusCircle from "svelte-material-icons/MinusCircle.svelte";
  import { omit } from "../lib/utils";

  export let variant = "warning";
  export let title = '';
  export let text = null;
  export let icon = true;
  export let filled = false;
  export let outlined = false;
  export let show = false; // TODO: Work on this.

  $: props = {
    ...omit($$props, "variant", "filled", "outlined"),
    class: `alert ${variant} ${$$props.class || ""}`,
  };
</script>

<style lang="scss">
  section {
    --white: rgb(241, 242, 237);
    --success-fore: #9AE59A;
    --success-back: #040f04;
    --error-fore: #F57D75;
    --error-back: rgb(34, 6, 3);
    --warning-fore: rgb(239, 152, 46);
    --warning-back: rgb(23, 15, 4);
    --info-fore: #5FB2F2;
    --info-back: rgba(2, 15, 25);
    --info-back-filled: rgba(10, 124, 250);
    --warning-back-filled: rgb(239, 152, 46);
    --success-back-filled: rgb(44, 164, 44);
    --error-back-filled: rgb(160, 12, 12);
    align-items: center;
    display: flex;
    margin: 0.25rem;
    position: sticky;
    top: 0;
    left: 0;
  }

  article {
    padding: 1rem;
  }

  article.title {
    font-weight: 600;
    width: 10%;
  }

  article.text {
    width: 85%;
  }

  aside {
    align-self: center;
    padding-left: 0.25rem;
    height: 100%;
    width: 5%;
  }

  .info {
    color: var(--info-fore);
    background-color: var(--info-back);
  }
  
  .info.filled {
    color: var(--white);
    background-color: var(--info-back-filled);
  }

  .info.outlined {
    border: 1px solid var(--info-back-filled);
  }

  .warning {
    color: var(--warning-fore);
    background-color: var(--warning-back);
  }

  .warning.filled {
    color: var(--white);
    background-color: var(--warning-back-filled);
  }

  .warning.outlined {
    border: 1px solid var(--warning-back-filled);
  }

  .success {
    color: var(--success-fore);
    background-color: var(--success-back);
  }
  
  .success.filled {
    color: var(--white);
    background-color: var(--success-back-filled);
  }
  
  .success.outlined {
    border: 1px solid var(--success-back-filled);
  }

  .error {
    color: var(--error-fore);
    background-color: var(--error-back);
  }
  
  .error.filled {
    color: var(--white);
    background-color: var(--error-back-filled);
  }

  .error.outlined {
    border: 1px solid var(--error-back-filled);
  }
</style>

{#if show}
  <section {...props} class:variant class:filled class:outlined transition:slide={{ duration: 300}}>
    {#if icon}
      <aside transition:slide={{ duration: 300}}>
        {#if variant === 'info'}
          <Information size="1.5rem" />
        {:else if variant === 'warning'}
          <Alert size="1.5rem" />
        {:else if variant === 'success'}
          <ThumbUp size="1.5rem" />
        {:else if variant === 'error'}
          <MinusCircle size="1.5rem" />
        {/if}
      </aside>
    {/if}
    {#if title !== ''}
      <article class="title">{title}</article>
    {/if}
    <article class="text" transition:fly={{ delay: 100, x: 200, duration: 300}}>{text}</article>
  </section>
{/if}
