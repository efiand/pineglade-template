<script lang="ts">
	import { StatusCodes } from 'http-status-codes';
	import { page } from '$app/stores';
</script>

<p>
	{#if $page.status === StatusCodes.NOT_FOUND}
		Страница не найдена.
	{:else}
		{$page.error?.message}.
	{/if}

	<a href="mailto:dev@pineglade.ru">Связаться с разработчиком</a>.
</p>
