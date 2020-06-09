<script>
  import Plus from "svelte-material-icons/Plus.svelte";

  import { onMount } from "svelte";
  import { getEventsAction } from "../lib/event";
  import { omit } from "../lib/utils";

  import Spinner from "./Spinner.svelte";

  export let tag = "button";
  export let type = "";
  export let size = "";
  export let href = "";
  export let nativeType = "button";
  export let loading = false;
  export let inverted = false;
  export let outlined = false;
  export let rounded = false;
  export let disabled = false;
  export let block = false;
  export let text = false;
  export let link = false;
  export let iconLeft = null;
  export let iconRight = null;
  export let iconOnly = false;
  export let iconPack = null;
  export let onclick = null;
  let iconSize = "";

  onMount(() => {
    if (!["button", "a"].includes(tag))
      throw new Error(`'${tag}' cannot be used as a tag for a button`);
  });

  $: props = {
    ...omit(
      $$props,
      "loading",
      "inverted",
      "nativeType",
      "outline",
      "rounded",
      "type"
    ),
    class: `button ${type} ${size} ${iconOnly} ${$$props.class || ""}`,
  };

  $: {
    if (!size || size === "medium") {
      iconSize = "small";
    } else if (size === "large") {
      iconSize = medium;
    } else {
      iconSize = size;
    }
  }
</script>

<style>
  button:disabled {
    cursor: default;
  }
  button {
    background-color: var(--white);
    color: var(--bg);
    cursor: pointer;
    font-family: Roboto, Helvetica, sans-serif;
    font-family: Helvetica, sans-serif;
    font-size: 1.2rem;
    font-weight: 500;
    letter-spacing: 0.75px;
    text-decoration: none;
    text-transform: uppercase;
    will-change: transform, opacity;
    margin: 1rem 0;
    padding: 0 16px;
    display: -ms-inline-flexbox;
    display: inline-flex;
    position: relative;
    align-items: center;
    justify-content: center;
    box-sizing: border-box;
    height: 36px;
    border: none;
    outline: none;
    line-height: inherit;
    user-select: none;
    overflow: hidden;
    vertical-align: middle;
  }

  .primary {
    background-color: var(--brand);
  }

  .accent {
    background-color: var(--dark-accent);
  }

  .success {
    background-color: var(--success);
  }

  .info {
    background-color: var(--info);
  }

  .warning {
    background-color: var(--warning);
  }

  .danger {
    background-color: var(--danger);
    color: var(--white);
  }

  .rounded {
    border-radius: 15px;
  }

  .link {
    background-color: blue;
    color: var(--white);
  }

  .text {
    background-color: unset;
    color: var(--white);
    text-decoration: underline;
  }

  button:disabled {
    background-color: var(--bg);
    border: 1px solid var(--white);
    color: var(--white);
  }

  .block {
    width: 100%;
  }

  .iconOnly {
    background-color: transparent;
    color: var(--white);
    padding: 0;
    margin: 0;
  }
</style>

{#if tag === 'button'}
  <button
    {...props}
    type={nativeType}
    class:inverted
    class:loading
    class:outlined
    class:rounded
    class:block
    class:text
    class:link
    class:iconOnly
    on:click={onclick}
    {disabled}>
    {#if iconLeft}
      <svelte:component this={iconLeft} />
    {/if}
    {#if loading}
      <Spinner size="tiny" />
    {:else if !iconOnly}
      <span>
        <slot />
      </span>
    {/if}
    {#if iconRight}
      <svelte:component this={iconRight} />
    {/if}
  </button>
{:else if tag === 'a'}
  <a
    {...props}
    type={nativeType}
    class:inverted
    class:loading
    class:outlined
    class:rounded
    class:block
    class:text
    class:link
    on:click={onclick}
    {href}>
    {#if iconLeft}LeftIcon{/if}
    <span>
      <slot />
    </span>
    {#if iconRight}RightIcon{/if}
  </a>
{/if}
