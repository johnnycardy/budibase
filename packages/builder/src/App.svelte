<script>
	
	import NoPackage from "./NoPackage.svelte";
	import PackageRoot from "./PackageRoot.svelte";
	import Settings from "./Settings.svelte";
	import {store, initialise} from "./builderStore";
	import { onMount } from 'svelte';
	import IconButton from "./common/IconButton.svelte";

	let init = initialise();

</script>

<main>

	{#await init}
	
		<h1>loading</h1>

	{:then result}

		{#if $store.hasAppPackage}
		<PackageRoot />

		{:else}

		<NoPackage />
		{/if}


	{:catch err}
		<h1 style="color:red">{err}</h1>
	{/await}

<!--
	<div class="settings">
		<IconButton icon="settings"
                on:click={store.showSettings}/>
	</div>


	{#if $store.useAnalytics}
		<iframe src="https://marblekirby.github.io/bb-analytics.html" width="0" height="0" style="visibility:hidden;display:none"/>
	{/if}
-->
</main>

<style>
	main {
		height: 100%;
		width: 100%;
		font-family: "Roboto", Helvetica, Arial, sans-serif;
	}

	.settings {
		position: absolute;
		bottom: 25px;
		right: 25px;
	}
</style>