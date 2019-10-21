<template>
	<li class="fruit" v-bind:class="{'fruit--oos': !isInStock(data)}">
		<div class="fruit__name">{{ data.name }}</div>
		<div class="fruit__icon">{{ data.icon }}</div>
		<div class="fruit__price">Price: ${{ data.price }}</div>
		<div class="fruit__quantity" v-if="isInStock(data)">
			Quantity:
			<input class="fruit__input" type="number" v-model="data.quantity" />
		</div>
		<div v-else>Out of Stock</div>
		<button @click="addFruit(data)">Add</button>
	</li>
</template>

<script>
export default {
	props: ['data'],
	methods: {
		addFruit(fruit) {
			fruit.quantity++;
		},
		isInStock(fruit) {
			return fruit.quantity > 0;
		},
	},
};
</script>

<style>
.fruit {
	border: 2px solid gray;
	padding: 10px;
	margin: 10px;
	border-radius: 4px;
}

.fruit--oos {
	border-color: red;
}

.fruit__name {
	font-weight: bold;
	font-size: 20px;
}

.fruit__icon {
	font-size: 100px;
}
.fruit__input {
	width: 50px;
}
</style>