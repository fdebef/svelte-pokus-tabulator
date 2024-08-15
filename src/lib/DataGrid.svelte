<script lang="ts">
	import { sampleData as data } from './SampleData';
	import Tabulator from './Tabulator.svelte';
	import type { ColumnDefinition } from 'tabulator-tables';

	const colDefs: ColumnDefinition[] = [
		{ title: 'Provozovnax', field: 'provozovna', resizable: true },
		{ title: 'Id', field: 'id', resizable: true },
		{ title: 'Název', field: 'nazev', resizable: true },
		{ title: 'Id Zbozi', field: 'id_zbozi', resizable: true },
		{ title: 'PDK', field: 'pdk', resizable: true },
		{ title: 'Sklad', field: 'sklad', resizable: true },
		{ title: 'Prodej', field: 'prodej', resizable: true },
		{
			title: 'NCena BD Celkem',
			field: 'ncena_bd_celkem',
			resizable: true
		},
		{
			title: 'PCena BD Celkem',
			field: 'pcena_bd_celkem',
			resizable: true
		},
		{ title: 'OP', field: 'op', width: 30 }
	];
</script>

<div class="w-96">
	<Tabulator {data} columns={colDefs} />
</div>
