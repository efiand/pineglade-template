<script lang="ts">
	export let alt = '';
	export let block = true;
	export let filename: string;
	export let height: string | null = null;
	export let width: string | null = null;
</script>

<img class:block src="/img/{filename}" {alt} {width} {height} />

<style>
	.block {
		display: block;
	}
</style>
