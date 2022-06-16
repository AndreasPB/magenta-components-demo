<script lang="ts">
	import DarkLogo from '$lib/static/magenta-logo-byline-dark.svg';
	import LightLogo from '$lib/static/magenta-logo-byline.svg';

	interface Link {
		path: string;
		name: string;
	}

	export let links: Link[] = [];

	const isDarkMode = (): string => {
		if (typeof window !== 'undefined') {
			return window.matchMedia('(prefers-color-scheme: dark)').matches ? DarkLogo : LightLogo;
		}
		return LightLogo;
	};

	let dynamicLogo: string = isDarkMode();

	if (typeof window !== 'undefined') {
		window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', function (e) {
			dynamicLogo = e.matches ? DarkLogo : LightLogo;
		});
	}
</script>

<nav>
	<ul>
		<li>
			<a href="/"><img src={dynamicLogo} alt="Logo" width="150em" /></a>
		</li>
	</ul>
	<ul>
		{#each links as link}
			<li><a href={link.path}>{link.name}</a></li>
		{/each}
	</ul>
</nav>
