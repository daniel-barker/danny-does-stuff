<script>
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	let { children } = $props();
</script>

<div class="flex min-h-screen flex-col bg-stone-200">
	<Header />
	<main class="flex-1">
		<div class="mx-auto max-w-6xl">
			{@render children()}
		</div>
	</main>
	<Footer />
</div>
