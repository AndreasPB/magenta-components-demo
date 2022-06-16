<script lang="ts">
	import DarkLogo from '$lib/static/magenta-logo-byline-dark.svg';
	import LightLogo from '$lib/static/magenta-logo-byline.svg';

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
		<img src={dynamicLogo} alt="Dark logo" width="150em" />
	</ul>
	<ul>
		<li><a href="/">Link</a></li>
		<li><a href="/">Link</a></li>
		<li><a href="/" role="button">Home</a></li>
	</ul>
</nav>
