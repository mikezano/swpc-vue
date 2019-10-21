<template>
	<div>
		<h1>Fruits</h1>
		<ul class="fruits" v-if="fruits.length > 0">
			<li class="fruit" v-for="fruit in fruits" v-bind:key="fruit.id">
				<Fruit v-bind:data="fruit"></Fruit>
			</li>
		</ul>
		<h1>Total Value: ${{ totalValue }}</h1>
	</div>
</template>

<script>
import Fruit from "../components/Fruit.vue";
export default {
	name: "fruits",
	data() {
		return {
			fruits: []
		};
	},
	created() {
		fetch("https://my-json-server.typicode.com/mikezano/zson/fruits")
			.then(response => response.json())
			.then(json => {
				this.fruits = json;
			});
	},
	components: {
		Fruit
	},
	computed: {
		totalValue() {
			return this.fruits.reduce((sum, fruit) => {
				return sum + fruit.price * fruit.quantity;
			}, 0);
		}
	}
};
</script>

<style scoped>
.fruits {
	display: flex;
	flex-wrap: wrap;
	list-style-type: none;
}
</style>