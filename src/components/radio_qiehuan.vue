<template>
  <div>
  	<h3>{{text}}</h3>
  	<div>
  		<input type="radio" id='first' name="" value="firstOne" v-model='raval'/>
  		<label for="first">first</label>
  		<br>
		<input type="radio" id='second' name="" value="secondOne" v-model='raval'/>
  		<label for="second">second</label>
  	</div>

  	<div v-if="raval=='firstOne'">显示：first</div>
	<div v-else>显示：second</div>
  </div>
</template>

<script>
export default {
	name:"radioqh",
	data () {
	    return {
	      text: '单选切换',
	      raval:'' 
	    }
	 }
}
</script>

<style>

</style>
