<template>
  <h1>{{ msg }}</h1>
  <input 
    type="text" 
    v-model="msg"> 

  <h1>{{  checked }}</h1>  
  <input type="checkbox" v-model="checked">
</template>
<!-- :value="msg" @input="msg = $event.target.value"> -->
<!-- 한글 입력시 v-model이 아닌 위의 방식으로 양방향 데이터 바인딩 구축 -->
<script>
export default {
  data() {
    return {
      msg: 'Hello World!',
      checked: false
    }
  },
  // methods: {
  //   handler(event) {
  //     console.log(event.target.value)
  //     this.msg = event.target.value // 양방향 데이터 바인딩
  //   }
  // }
}
</script>

<style scoped>

</style>