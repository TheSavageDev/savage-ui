<script>
  import Spinner from "../components/Spinner.svelte";
</script>

<style>
  article {
    padding: 0.125rem;
  }
</style>

<svelte:head>
  <title>SavageUI</title>
</svelte:head>
<article>
  <h3>Tiny</h3>
  <Spinner size="tiny" />
  <h3>Small</h3>
  <Spinner size="small" />
  <h3>Medium</h3>
  <Spinner size="medium" />
  <h3>Large</h3>
  <Spinner size="large" />
  <h3>Huge</h3>
  <Spinner size="huge" />
  <h3>Enormous</h3>
  <Spinner size="enormous" />
  <h3>Gigantic</h3>
  <Spinner size="gigantic" />
  <h3>Stupid</h3>
  <Spinner size="stupid" />
</article>
