<template>
	<div>
		<h1>{{title}}</h1>
		<ul class="fruits">
			<Fruit v-for="fruit in fruits" v-bind:key="fruit.id" :data="fruit" />
		</ul>
		<h2>Total Value: ${{totalValue}}</h2>
	</div>
</template>

<script>
import Fruit from '../components/Fruit.vue';
export default {
	data() {
		return {
			title: 'Fruits R Us',
			fruits: [],
		};
	},
	created() {
		fetch('https://my-json-server.typicode.com/mikezano/zson/fruits')
			.then(response => response.json())
			.then(json => {
				this.fruits = json;
			});
	},
	components: {
		Fruit,
	},
	computed: {
		totalValue() {
			return this.fruits.reduce((sum, fruit) => {
				return sum + fruit.price * fruit.quantity;
			}, 0);
		},
	},
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
body {
	font-family: 'Roboto';
}

.fruits {
	display: flex;
	flex-wrap: wrap;
	list-style-type: none;
}
</style>
