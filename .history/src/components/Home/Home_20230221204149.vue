<template>
  <div class="home">
    <p ref="op">this is op</p>
  </div>
</template>

<script lang='ts'>
import { defineComponent, onMounted, ref } from 'vue'
export default defineComponent({
  setup () {
    let op = ref()
    onMounted(() => {
      console.log('on mounted', op.value);
      
    })
    return {
      
    }
  }
})
</script>
 
<style lang="less" scoped>
  
</style>