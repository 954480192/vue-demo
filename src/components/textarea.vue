<template>
  <div>
  	<h3>{{text}}</h3>
  	<textarea v-model='texts'></textarea>
  	<div v-html='texts'></div>
  </div>
</template>

<script>
export default {
	name:"textarea",
	data () {
	    return {
	      text: '多行文本x',
	      texts:'',
	      text_html:''   
	    }
	 }
}
</script>

<style>

</style>
