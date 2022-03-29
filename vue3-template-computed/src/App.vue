<template>
  <h1 @click="activate"
      :class="{ active: isActive }"> 
    Hello?!({{ isActive }})
  </h1> 
  <h1 
    :style="[fontStyle, backgroundStyle]"
    @click="changeStyle">
    Style Binding
  </h1>
</template>

<script>
// :class="{ active: isActive }" 
// 클래스에 active를 넣고 싶을 때 isActive의 영향을 받아서 isActive의 값이 true면 active로 변경(클래스 바인딩)
export default {
  data() {
    return {
      isActive: false,
      fontStyle: {
        color: 'orange',
        fontSize: '30px'
      },
      backgroundStyle: {
        backgroundColor: 'black'
      }
    }
  },
  methods: {
    activate() {
      this.isActive = true
    },
    changeStyle() {
      this.fontStyle.color = 'red'
      this.fontStyle.fontSize = '50px'
    }
  }
}
</script>

<style scoped>
  .active {
    color: red;
    font-weight: bold;
  }
</style>