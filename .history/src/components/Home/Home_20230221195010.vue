<template>
  <div>
    <p>{{ newNum }}</p>
    <div @click="hdClick">按钮</div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  setup() {
    let newNum = ref(20)
    const hdClick = () => {
      console.log(newNum)
    }
    return {
      newNum,
      hdClick
    }
  }
})
</script>