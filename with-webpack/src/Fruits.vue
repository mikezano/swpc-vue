<template>
<div>
	<ul class="fruits">
		<li 
			v-for="fruit in fruits"
			:key="fruit.id">
			<Fruit :data="fruit" @updated="calculateTotal()" />
		</li>
	</ul>
	<div>Total: {{total}}</div>
</div>
</template>

<script>
import Fruit from './Fruit.vue';
export default {
	data(){
		return {
			fruits:[],
			total: 0
		};
	},
	created(){
		fetch('https://my-json-server.typicode.com/mikezano/zson/fruits')
		.then(response => response.json())
		.then(json => {
			this.fruits = json
		})
	},
	watch:{
		fruits: function(newFruits, oldFruits){
			this.total = newFruits.reduce((total, fruit)=>{
				return total + (fruit.quantity * fruit.price);
			},0);
			debugger;
		}
	},
	components:{
		Fruit
	}
}
</script>

<style>
.fruits{
	display:flex;
	flex-wrap: wrap;
	list-style-type:none;
}
</style>