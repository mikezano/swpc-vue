<template>
	<li class="fruit" v-bind:class="{ 'fruit--oos': !isInStock() }">
		<div class="fruit__name">{{ data.name }}</div>
		<div class="fruit__icon">{{ data.icon }}</div>
		<div class="fruit__price">${{ data.price }}</div>
		<div class="fruit__quantity" v-if="isInStock()">
			Quantity:
			<input class="fruit__input" type="number" v-model="data.quantity" />
		</div>
		<div v-else>Out of stock</div>
		<button @click="addQuantity()">Add</button>
	</li>
</template>

<script>
export default {
	name: "Fruit",
	props: ["data"],
	methods: {
		addQuantity() {
			this.data.quantity++;
		},
		isInStock() {
			return this.data.quantity > 0;
		}
	}
};
</script>

<style scoped>
.fruit {
	border: 2px solid gray;
	border-radius: 5px;
	padding: 10px;
	margin: 10px;
}
.fruit--oos {
	border-color: red;
}
.fruit__name {
	font-size: 20px;
	font-weight: bold;
}
.fruit__icon {
	font-size: 80px;
}
.fruit__input {
	width: 50px;
}
</style>