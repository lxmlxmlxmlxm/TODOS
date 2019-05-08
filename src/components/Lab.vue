<template>
	<div class="lab">
	 <!-- <a-checkbox @change="onChange" class='com-xz' >
	 <label @dblclick="a"> {{list.newTodo}} </label>
	 <input id="aa" style="display:none"></a-checkbox>
	  <a href @click.prevent='deleteMe' class='com-delete'>删除</a>
	 -->
	 <a-checkbox @change="onChange" class='com-xz' >
	
	<label class="content_main" @dblclick="toEdit('show')"  v-if="visible" >
          {{list.newTodo}}
        </label>
        <a-input  
        v-model="list.newTodo" 
        style="width:400px"  @blur="toEdit('hide')"  v-else>
        </a-input>
		
	</a-checkbox>
	<a href @click.prevent='deleteMe' class='com-delete'>删除</a>
</div>
 
</template>
	
<script>
	export default {
  props: ['list'],
  data() {
  	return {
  		checked: [],
		visible:true
  	}
  },
  methods: {
    onChange (e) {
	  this.list.che= e.target.checked
      console.log(`checked = ${e.target.checked}`)
    },
    toEdit(value) {
                this.visible = !(value === 'show')
                // document.getElementById("ainput").focus()
    		    },
    
    
          //是否可以编辑
	deleteMe(){
				this.$emit('de',this.list.id);
	}
  },
}
</script>

<style>
</style>
