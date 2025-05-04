<script>
	let month = new Date().toLocaleString('default', { month: 'long' });
	let year = new Date().getFullYear();

	import { onMount } from 'svelte';

	onMount(() => {
		// Load Calendly widget script
		const script = document.createElement('script');
		script.src = 'https://assets.calendly.com/assets/external/widget.js';
		script.async = true;
		document.body.appendChild(script);
	});

	function openCalendly() {
		if (typeof Calendly !== 'undefined') {
			Calendly.initPopupWidget({url: 'https://calendly.com/evolsquirrel/30min'});
		}
		return false;
	}
</script>

<svelte:head>
	<link href="https://assets.calendly.com/assets/external/widget.css" rel="stylesheet">
</svelte:head>

<div class="flex flex-wrap justify-center gap-4 p-6">
	<a
		href="tel:+18452142223"
		class="rounded-xl bg-blue-600 px-6 py-3 text-white shadow hover:bg-blue-700">Text me</a
	>
	<a
		href="mailto:dan@dan-barker.com"
		class="rounded-xl bg-green-600 px-6 py-3 text-white shadow hover:bg-green-700">Email me</a
	>
	<a 
		href="#" 
		on:click={openCalendly}
		class="rounded-xl bg-stone-800 px-6 py-3 text-white shadow hover:bg-stone-900"
		>Book Online</a
	>
</div>

<footer class="text-center text-sm text-stone-600">
	© {month}
	{year} Danny Does Stuff — Buffalo, NY
</footer>
