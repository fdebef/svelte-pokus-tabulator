<script lang="ts">
	import {
		type ColumnDefinition,
		// ResizeColumnsModule,
		// ResponsiveLayoutModule,
		TabulatorFull as Tabulator
	} from 'tabulator-tables';
	import { onMount } from 'svelte';

	export let data: unknown[];
	export let columns: ColumnDefinition[] | undefined = undefined;

	let tableComponent: HTMLDivElement;

	console.log('THIS IS COLS: ', columns);

	// Tabulator.registerModule(ResizeColumnsModule);
	// Tabulator.registerModule(ResponsiveLayoutModule);

	onMount(() => {
		new Tabulator(tableComponent, {
			data: data, //link data to table
			columns: columns || [], //define table columns
			reactiveData: true, //enable data reactivity
			rowHeight: 24,
			layout: 'fitDataTable',
			layoutColumnsOnNewData: true,
			resizableColumnFit: true,
			resizableRows: true,
			resizableRowGuide: true,
			height: 400,
			renderVerticalBuffer: 300
		});
	});
</script>

<div bind:this={tableComponent}></div>

<svelte:head>
	<link
		href="https://unpkg.com/tabulator-tables@4.9.1/dist/css/tabulator.min.css"
		rel="stylesheet"
	/>
</svelte:head>
