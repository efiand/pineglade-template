<script lang="ts">
	import '$lib/styles/app.scss';
	import { DOMAIN, PROJECT } from '$lib/utils/constants';
	import Footer from '$lib/components/Footer.svelte';
	import Header from '$lib/components/Header.svelte';
	import { page } from '$app/stores';

	let title: string;
	let description: string;
	let url: string;

	$: title = `${PROJECT}: ${$page.data.title}`;
	$: description = `Страница «${$page.data.title}» сайта «${PROJECT}».`;
	$: url = `${DOMAIN}${$page.url.pathname}`;
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={description} />
	<link rel="canonical" href={url} />
	<meta property="og:site_name" content={PROJECT} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={description} />
	<meta property="og:url" content={url} />
</svelte:head>

<div class="page">
	<Header />

	<main>
		<slot />
	</main>

	<Footer />
</div>

<style lang="scss">
	.page {
		display: grid;
		grid-template-rows: min-content 1fr min-content;
		min-height: 100vh;
	}
</style>
