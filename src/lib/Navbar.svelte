<script lang="ts">
	export let appName = '';
</script>

<div class="navbar bg-base-100 shadow-lg">
	<div class="flex-1">
		<a href="/" class="btn btn-ghost space-x-2">
			<img src="/logo.svg" alt="Nimbyte logo" width="40" height="40" />
			{#if appName}
				<span>{appName}</span>
			{/if}
		</a>
	</div>
	<div class="navbar-end">
		<slot name="navbar-end" />
	</div>
</div>
