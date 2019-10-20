<template>
<div class="fruit" v-bind:class="{'fruit--out': data.quantity <= 0}">
	<div class="fruit__name">{{data.name}}</div>
	<div class="fruit__icon">{{data.icon}}</div>
	<div class="fruit__price">Price: {{data.price}}</div>
	<div class="fruit__quantity" v-if="data.quantity <= 0">(Out Of Stock)</div>
	<div class="fruit__quantity" else>Quantity: 
		<input class="fruit__input" type="number" v-model.number="data.quantity" />
	</div>
	<button @click="data.quantity++">Add</button>
</div>
</template>

<script>
export default {
	props: ['data'],
	methods: {
		
	}
}
</script>

<style>
.fruit{
	border:2px solid gray;
	border-radius: 4px;
	margin: 1rem;
	padding:1rem;
	display:flex;
	flex-direction: column;
	align-items:center;

}
.fruit--out{
	border-color: red;
}
.fruit__icon{
	font-size:80px;
}
.fruit__input{
	width:50px;
}

</style>