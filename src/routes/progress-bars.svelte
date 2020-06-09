<script>
  import ProgressBar from "../components/ProgressBar.svelte";
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
  <title>SavageUI - Progress Bars</title>
</svelte:head>
<article>
  <h2>Progress Bars</h2>
  <ProgressBar value={10} color="red" />
  <ProgressBar value={20} color="orange" />
  <ProgressBar value={30} color="yellow" />
  <ProgressBar value={40} color="green" />
  <ProgressBar value={50} color="blue" />
  <ProgressBar value={60} color="purple" />
  <ProgressBar value={70} />
  <ProgressBar value={80} />
  <ProgressBar value={90} />
  <ProgressBar value={100} color="america" />
</article>
