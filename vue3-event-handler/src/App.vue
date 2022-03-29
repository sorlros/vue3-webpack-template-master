<template>
  <button @click="handler('hi', $event)">
    click 1
  </button>
  <button @click="handler('hello', $event)">
    click 2
  </button>

  <button @click="handlerA(), handlerB()">
    Click me
  </button>

  <a 
    href="https://google.com"
    target="_blank"
    @click.prevent.once="handler2">
    Google
  </a>

  <div
    class="parent"
    @click.capture.stop="handlerA"> <!-- .capture 이벤트 캡쳐링 하위요소의 이벤트가 발생시 부모요소의 이벤트부터 먼저 실행시키고 하위요소의 이벤트 실행  -->
    <div
      class="child"
      @click.stop="handlerB"> <!-- .stop 이벤트 버블링 방지 -->

     </div>
  </div>
  
  <div
    class="parent"
    @click="handlerA"> <!-- .self 해당영역에서만 이벤트 발생시 return -->
    <div
      class="child">

     </div>
  </div>

  <div
    class="parent2"
    @wheel.passive="handlerA2"> <!-- .passive 로직의 처리와 화면의 스크롤을 독립 부하 감소 사용자에게 쾌적한 환경제공 -->
    <div class="child2"></div>
  </div>

  <input 
    type="text"
    @keydown.ctrl.shift.a="handler3"> <!-- .enter keydown을 했을때 엔터키를 눌러야지만 이벤트발생, .a .b 여러 문자중 케밥케이스로 만들었을때도 동일한 .enter와 동일  -->
</template>

<script>
export default {
  methods: {
    handler(msg, event) {
      console.log(msg)
      console.log(event)
    },
    handlerA(event) {
      console.log(event.target)
      console.log(event.currentTarget)
      console.log('A')
    },
    handlerB() {
    //  event.stopPropagation() // 이벤트 버블링 방지
      console.log('B')
    },
    handlerA2(event) {
      for (let i = 0; i < 10000; i+= 1) {
        console.log(event)
      }
      
    },
    handler2() {
    //  event.preventDefault()
      console.log('ABC')
    },
    handler3(event) {
    //   if (event.key === 'Enter') {
    //     console.log('Enter')
    //   }
      console.log('Enter')
    }
  }
}
</script>

<style scoped lang="scss">
  .parent {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    .child {
      width: 100px;
      height: 100px;
      background-color: orange;
    }
  }

  .parent2 {
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    overflow: auto;
    .child2 {
      width: 100px;
      height: 2000px;
      background-color: orange;
    }
  }
</style>