<template>
  <div id="app">
    <div id="nav">
			<a ></a>
      <router-link :to="{name:'home',query: { userId: 1111}}">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
   <router-view/>
  </div>
</template>

 <script>
import Com from './components/Com.vue'
export default {
	//this.$router.push({ name: 'home', query: { plan: 'private' }})
	components: {
			Com
		} ,
	}
	
</script> 
<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
