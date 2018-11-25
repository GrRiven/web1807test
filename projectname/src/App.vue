<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <HelloWorld/>
    <MyComponent title="我的世界" @msgEvent = "getMsg" />
    <p v-show = "!falg" v-for="(item,index) in arr"  :key="index">{{item}}</p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import MyComponent from './components/MyComponent'
export default {
  name: 'App',
  data(){
    return{
      names:["gg","ww","ee"],
      msg:"",
      falg:false,
      arr:[]
    }
  },
  components: {
    HelloWorld,
    MyComponent
  },
  methods:{
    getMsg(value){
      this.msg = value;
      this.arr.push(this.msg)
      this.flag = true;
      console.log(value);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
