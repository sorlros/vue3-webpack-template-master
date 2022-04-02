<template>
  <!-- <h1 ref="hello">
    Hello World
  </h1> -->

  <Hello ref="hello" />
</template>

<script>
import Hello from '~/components/Hello'

export default {
  components: {
    Hello
  },
  // created() { // component가 생성된 직후
  //   console.log(this.$refs.hello)
  //   // undefined
  // },
  mounted() { // html이 component에 연결된 직 후 
    //this.$refs.hello
    console.log(this.$refs.hello.$el)
    // component를 refs를 통해 참조할때는 참조된 이름의 뒤에 $el 속성을 붙여야 참조가능

    console.log(this.$refs.hello.$refs.good)

    // const h1El = document.querySelector('h1')
    // console.log(h1El.textContent)
  }
}
</script>

<style scoped>

</style>