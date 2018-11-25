<template>
<div>
{{msg}}<br/>
{{1+1}}<br/>
{{arr}}<br/>
{{myh1}}
<div v-html="myh1"></div>
<div v-bind:class="myclass"></div>
<template v-if="flag">
  <p>孙悟空</p>
  <p>齐天大圣美猴王</p>
</template>
<template v-else>
  <p>六耳猕猴</p>
  <p>通臂猿猴</p>
</template>
<p v-show="flag">p1</p>
<p>p2</p>
<ul>
  <li v-for = "(item,index) in myarr" v-bind:key = "index">{{item}}</li>
</ul>
<p v-for = "(value,key,index) in obj" v-bind:key = "index">{{value}}-{{key}}-{{index}}</p>
<button type="button" @click="getMeser" name = "button">按钮</button>
<p v-once>{{num}}</p>
<p :style="{fontSize:'40px',color:'red'}">{{ getHello }}</p>
<p :style="[baseStyles]">{{ getJin }}</p>
<a href="#" @click.prevent = "upHref">去吧</a>
<div :class="[isClass ?'isis':'']">ddddd</div>
<div :class="[obj.name,{'active':isActive,'error':isError},flag ? 'flag':'']">
  123123123
</div>

<p>{{getGulong()}}</p>
</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      num:0,
      msg: 'Welcome to Your Vue.js App',
      arr:[0,1,2,3,4,5],
      myh1:"<h1>欢迎来到我的vue</h1>",
      myclass:"hello1",
      flag:false,
      hello:"heelo",
      isActive:true,
      isError:true,
      myarr:["老子","中庸","大学"],
      obj:{
        name:"菠萝",
        age:20
      },
      jinyong:"白马啸西风",
      gulong:"小李飞刀",
      baseStyles:{
        fontSize:"45px",
        color:"green",
        border:"1px solid green"
      },
      isClass:true
    }
  },
methods:{
  getMeser:function(value){
    this.num+=10;
  },
  getGulong:function(){
    return this.gulong + "----古龙"
  },
  upHref:function(){
    console.log("去吧");
  }
},
  computed:{
    getHello(){
      return this.hello.split("").reverse().join("")
    },
    getJin(){
      return this.jinyong+"---金庸"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
