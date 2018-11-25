<template lang="html">
  <div class="mycomponent" >
      hello:{{title}}
      <li v-for="(item,index) in names"  :key="index">{{item}}</li>
      <button @click= "setDet" type="button" name="button">awdadw</button>
  </div>
</template>

<script>
  export default {
    name:"MyComponent",
    data(){
      return{
            msg:"我是儿子的数据",
            
      }
    },
    props:{
      title:{
        type:String,
        required:true
      },
      names:{
        type:Array,
        default:function(){
          return [1,2,3]
        }
      }
    },
    methods:{
        setDet(event){
          this.$emit("msgEvent",this.msg)
        }
    }
  }
</script>
<style lang="css" scoped>

</style>
