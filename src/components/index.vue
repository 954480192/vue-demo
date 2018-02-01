<template>
  <div>
  	<h2>{{text}}</h2>
  	<textareaA></textareaA>
  	<radioqhA></radioqhA>
  	<tableA></tableA>
  </div>
</template>

<script>
import textareaA from './textarea'
import radioqhA from './radio_qiehuan'
import tableA from './table'
export default {
	name:"index",
	components:{textareaA,radioqhA,tableA},
	data () {
	    return {
	      text: '导航'   
	    }
	 }
}
</script>

<style>
*{margin: 0;padding: 0;}
#app{text-align: left;}
h3{background: gainsboro;}
</style>
