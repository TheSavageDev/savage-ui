<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
  main {
    display: flex;
    font-size: 1.6rem;
  }
  section {
    padding: 1rem;
    width: 80%;
  }
</style>


<main>
	<Nav {segment}/>
  <section>
	  <slot></slot>
  </section>
</main>
