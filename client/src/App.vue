<template>
	<apexchart width="500" type="line" :options="options" :series="series"></apexchart>
</template>

<script setup>
import { reactive } from 'vue';

const options = reactive({
	series: [
		{
			name: 'XYZ MOTORS',
			data: [30, 40, 45, 50, 49, 60, 70, 91],
		},
	],
	chart: {
		type: 'area',
		stacked: false,
		height: 350,
		zoom: {
			type: 'x',
			enabled: true,
			autoScaleYaxis: true,
		},
		toolbar: {
			autoSelected: 'zoom',
		},
	},
	dataLabels: {
		enabled: false,
	},
	markers: {
		size: 0,
	},
	title: {
		text: 'Euro',
		align: 'left',
	},
	fill: {
		type: 'gradient',
		gradient: {
			shadeIntensity: 1,
			inverseColors: false,
			opacityFrom: 0.5,
			opacityTo: 0,
			stops: [0, 90, 100],
		},
	},
	yaxis: {
		labels: {
			formatter: function (val) {
				return (val / 1000000).toFixed(0);
			},
		},
		title: {
			text: 'Price',
		},
	},
	xaxis: {
		type: 'datetime',
	},
});

const series = reactive([
	{
		name: 'series-1',
		data: [30, 40, 45, 50, 49, 60, 70, 91],
	},
]);
</script>
