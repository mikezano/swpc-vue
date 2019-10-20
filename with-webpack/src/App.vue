<template>
  <div id="app">
    <h2>{{ message }}</h2>
	<Fruits />
  </div>
</template>

<script>

import Fruits from './Fruits.vue';
export default {
  data() {
    return {
      message: 'Fruits R Us',
    };
  },
  components:{
	  Fruits
  }
};
</script>

<style>
#app {
  font-size: 18px;
  font-family: 'Roboto', sans-serif;
  display:flex;
  flex-direction:column;
  align-items:center;
}
</style>