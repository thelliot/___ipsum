<script>
import Header from './Header.svelte'
import OKBOOMER from './OKBOOMER.svelte'
</script>

<Header title="OK BOOMER" />
<main>
	<OKBOOMER />
</main>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
	}

	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}
</style>