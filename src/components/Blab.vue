<template>
	<div class="blab">

		<Lab v-for='c, index in list'
               :list='c'
			   :key='c.id'
			   @de='del'
			   v-model="c.che"
			   >
	    </Lab>
	 <a-button  @click.prevent='deleteAll' >勾选删除</a-button>	
	</div>
</template>

<script>
     import Lab from './Lab.vue'
	 export default {
	 	 components: {
	 		Lab
	    	},
			data() {
				return {
					check: true
				}
			},
		 props: ['list'],
		 methods: {
		 	del(id) {
		 		this.$emit('del',id);
		 	},
			deleteAll(){
				console.log(this.list);
				this.$emit('delAll',this.list);
			}
		 },
	 	}
	 	
</script>

<style>
	
</style>
