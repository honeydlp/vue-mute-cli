<template>
  <div>
    <div v-on:click="value = !value">
      toast测试
    </div>
    <toast :text="text" :value="value" ></toast>
  </div>
</template>

<script>
  import toast from 'components/toast'
  export default {
    data(){
      return{
        value:true,
        text:'哈哈'
      }
    },
    components:{
      toast
    }
  }
</script>

<style>

</style>
