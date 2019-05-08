<template>
  <div class="home">
  	<div id='root'>
    <Com @listfc="fc"></Com>
    <Blab v-bind:list="list" @del='dele' @delAll='deleteAll'></Blab>
		</div>
	</div>
</template>

<script>
// @ is an alias to /src

import HelloWorld from '../components/HelloWorld.vue'
import Com from '../components/Com.vue'
import Blab from '../components/Blab.vue'
export default {
	 components: {
		Com,Blab
   	} ,
		data() {
				return{ 
					 list:[]
				}
		},
		methods:{
			fc(res) {
				console.log("发射数据："+res.id);
				this.list.push(res) ;
				console.log(this.list);
				},
				dele(id){
					console.log(id);
					 this.list = this.list.filter((c) => c.id != id);
				},
				deleteAll(list){
					this.list=list;
					 this.list = this.list.filter((c) => c.che == false);
				},
		 el: '#root'
		}
	}
	
</script>

