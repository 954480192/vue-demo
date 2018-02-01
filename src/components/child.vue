<template>
  <div>
    {{ hello }}
	<p></p>
      <select v-model="op_val" @change="fankui">
	  	<option :disabled='op.disabled'  v-for="op in options" :value="op.val" >{{op.name}}
	  	</option>
	  </select>
	  <span >值：{{op_val}}</span>
  </div>
</template>

<script>
export default {
	props:{
      	options:{
      		type: Array
      	}
      },
	 data () {
	    return {
	      hello: 'Welcome to Your Vue.js App',
	      op_val:0      
	    }
	 },
	 methods:{
	 	fankui:function(e){
	 		this.$emit('fankuixx',e.target.value)
	 	}
	 }
}
</script>

<style>

</style>
