<template>
  <h1>{{ msg }}</h1>
  <input 
    type="text" 
    v-model.trim="msg">
    <!-- :value="msg" 
         @change="msg = $event.target.value" -->
</template>

<script>
export default {
  data() {
    return {
      msg: "Hello World"
    }
  },
  watch: {
    msg() {
      console.log(this.msg.trim())
      // 처음 msg는 숫자데이터이지만 input요소를 거치면 string타입으로 변경된다
      // v-model.number 는 숫자데이터로 유지
      // .trim()은 앞과 뒤의 공백을 제거 => v-model.trim
    }
  }
}
</script>

<style scoped>

</style>