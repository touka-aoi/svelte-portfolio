<script lang="ts">
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import github from '$lib/images/github.svg';
	import twitter from '$lib/images/twitter.svg';

	interface outerLink {
		name:string
		src:string
		loc:string
	}

	const links:outerLink[] = [
		{name: "github", src: "https://github.com/touka-aoi", loc:twitter},
		{name: "twitter", src: "https://twitter.com/touka_aoi", loc:github},
	];

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>




<section>
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app
	</h1>

	<h2>
		try editing <strong>src/routes/+page.svelte</strong>
	</h2>

	<Counter />
</section>

<!-- 外部リンク -->
	<section>
		<div class = "flex gap-8">  
			{#each links as {name, src, loc}}
				<div>
					<a href={src}>
						<img src={loc} alt={name} width=32px height=32px/>
					</a>
				</div>
			{/each}
		</div>
	</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
