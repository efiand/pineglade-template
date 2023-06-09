<script lang="ts">
	import { page } from '$app/stores';

	let isIndex: boolean;

	$: isIndex = $page.url.pathname === '/';
</script>

<header>
	<a href="/" aria-current={isIndex ? 'page' : null}> На главную </a>
	<nav />
</header>

<style lang="scss">
</style>
