<template>
  <h1> {{count}} </h1>
</template>

<script>
export default {
  data() {
    return {
      count: 2
    }
  },
  beforeCreate() { // component가 생성되기 직전에 실행
    console.log('Before Create', this.count) // undefined
  },
  created() {
    console.log('Created', this.count) // 2
    console.log(document.querySelector('h1')) // null
  },
  beforeMount() { // HTML과 연결되기 전 상태
    console.log('Before Mount')
    console.log(document.querySelector('h1')) // null
  },
  mounted() { // 화면에 실제 component가 출력 된 이후 실행
    console.log('Mounted')
    console.log(document.querySelector('h1'))
  }
}
</script>

<style scoped lang="scss">
  h1 {
    font-size: 50px;
    color: royalblue;
  }
</style>