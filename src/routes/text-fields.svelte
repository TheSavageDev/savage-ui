<script>
  import Input from "../components/Input.svelte";
  import Button from "../components/Button.svelte";

  let value = "";
</script>

<style>
  article {
    padding: 0.125rem;
  }

  article h2 {
    border-bottom: 0.125rem solid var(--brand-low-alpha);
    color: var(--white);
    font-size: 3rem;
    margin-bottom: 1rem;
    text-shadow: 1px 1px var(--brand-low-alpha);
  }
</style>

<svelte:head>
  <title>SavageUI - Text Fields</title>
</svelte:head>
<article>
  <h2>Input Fields</h2>
  <Input />
  <Input
    label="Basic"
    required
    bind:value
    message="Message Text"
    type="password"
    placeholder="Basic" />
  <Input
    label="Search"
    required
    bind:value
    message="Search"
    type="search"
    placeholder="Search" />
  <Input
    label="Outline"
    required
    bind:value
    outlined
    message="Message Text"
    placeholder="Outlined" />
  <Input
    label="Filled"
    required
    bind:value
    filled
    message="Message Text"
    placeholder="Filled" />
</article>
<article>
  <h2>Textareas</h2>
  <Button>Default</Button>
</article>
