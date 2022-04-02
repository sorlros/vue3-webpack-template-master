<template>
  <Child />
</template>
<!-- <Child :msg="msg" /> -->
<script>
import Child from '~/components/Child'
export default {
  components: {
    Child
  },
  // props: {
  //   msg: {
  //     type: String,
  //     default: ''
  //   }
  // }
}
</script>