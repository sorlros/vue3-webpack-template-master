<template>
  <MyBtn class="sorlros" style="color: red" title="Hello World">
    Banana
  </MyBtn>
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