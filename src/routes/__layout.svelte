<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
</script>

<div class="container">
	<Navbar
		links={[
			{ name: 'About', path: '/about' },
			{ name: 'Contact', path: '/contact' }
		]}
	/>
	<slot />
</div>
