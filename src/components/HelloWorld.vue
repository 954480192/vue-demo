<template>
  <div class="hello">
    <!-- <child-a :options='options' @fankuixx="xx"></child-a>
    <ul>
      <li v-for="i in list">{{i.name}}</li>
      <br>
      <li v-for="(v,k,i) in obj">{{i}}---{{k}}:{{v}}</li>
    </ul>
    <p>{{message}}</p>-->

    <index-a></index-a>
  </div> 
</template>

<script>
import childA from './child'
import indexA from './index'

export default {
  name: 'HelloWorld',
  components:{childA,indexA},
  methods:{
    xx:function(name){
      this.message="子组件已收到了："+name;
    }
  },
  data:function() {
    return {
      msg: 'Welcome to Your Vue.js App',
      message:"",
      list:[
        {
            id:"1",
            name:"fruit1"
        },
        {
          id:"2",
          name:"fruit2"
        }
      ],
      obj:{
        a:"a1",
        b:"b2"
      },
      options:[
        {
          name:'请选择',
          val:0,
          disabled:true
        },{
          name:'dd',
          val:1
        },{
          name:'ff',
          val:2
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
