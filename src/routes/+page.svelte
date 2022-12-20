<script lang="ts">
	import Fotter from "./Fotter.svelte"
	import { pageLink } from "./pagelink";
</script>

<section>
	<h1 class = "title">Toukaworks</h1>
	<div class = "flex gap-4 justify-center mt-4">
		{#each pageLink as {name}}
			<a href="/{name}" class = "text-violet-800 hover:text-violet-500 bold hover:no-underline">{name}</a>
		{/each}
	</div>
</section>


<Fotter />

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}
</style>
