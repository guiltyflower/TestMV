<script>
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher()

	export let value;

	function handleClick() {
		dispatch('change');
	}
	function handleChange() {
		value = !value;
	}
</script>



<div class="root" on:click={handleClick}>
	{#if value}
		<input
			type="checkbox"
			value="{value}"
			on:change ="{handleChange}"
			checked
			readonly
		/>
	{:else}
		<input
			type="checkbox"
			value="{value}"
			on:change ="{handleChange}"
			readonly
		/>
	{/if}
	<label><slot></slot> [current: {value}]</label>
</div>
