<template>
  <div>
  	<h3>{{text}}</h3>
  	
  	<div>
  		<input type="text" name="" :value='val' @click='ctable'/>
  	</div>
  	<table v-if='toggle'>
  		<tr>
  			<th v-for='(th,index) in table.thead' @click='sort(index)'>{{th.zh}}</th>
  		</tr>
  		<tbody>
  			<tr v-for='tr in table.tbody'>
  				<td v-for='td in tr' @click='tdval(td.zh)'>{{td.zh}}</td>
  			</tr>
  		</tbody>
  	</table>
  </div>
</template>

<script>
export default {
	name:"textarea",
	methods:{
		ctable:function(){
			this.toggle=!this.toggle;
		},
		tdval(zh){
			this.val=zh;
		},
		sort(index){
			var sot = this.table.thead[index].st;
			for (var i = 1; i < this.table.tbody.length; i++) {
				var pretr = this.table.tbody[i-1];
				var pretd = pretr[index].zh;
				var tr = this.table.tbody[i];
				var td = tr[index].zh;
				if((pretd<td&&sot)||(pretd>td&&!sot)){
					var f = pretr;
					this.table.tbody[i-1] = tr;
					this.table.tbody[i]=f;
				}
			}
			this.table.thead[index].st = !sot;
			this.table.tbody=Object.assign([],this.table.tbody);
		}
	},
	data () {
	    return {
	      text: '表格创建和排序选择',
	      toggle:false,
	      val:'',
	      table:{
	      	thead:[
	      		{
	      			zh:'th1',
	      			st:true
	      		},{
	      			zh:'th2',
	      			st:true
	      		}
	      	],
	      	tbody:[
				[
					{
		      			zh:'td11'
		      		},{
		      			zh:'td12'
		      		}
				],
				[
					{
		      			zh:'td21'
		      		},{
		      			zh:'td22'
		      		}
				]
	      	]
	      }
	    }
	 }
}
</script>

<style>

</style>
