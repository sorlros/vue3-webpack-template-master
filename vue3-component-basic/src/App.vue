<template>
  <MyBtn color="#000">Banana</MyBtn>
  <MyBtn 
    color="black">
    <span style="color: red">Banana</span>
  </MyBtn>
  <MyBtn large color="royalblue">Apple</MyBtn>
  <MyBtn :color="color"></MyBtn>
  <MyBtn></MyBtn>
  <MyBtn>Cherry</MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'
export default { 
  components: {
    MyBtn
  },
  data() {
    return {
      color: '#000'
    }
  }
}
</script>

<style scoped>

</style>