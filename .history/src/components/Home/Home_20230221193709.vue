<template>
  <div>
    <p>这是第一个组件</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, onBeforeMount, onMounted} from 'vue';
export default defineComponent({
  setup() {
    onBeforeMount(() => {
      console.log('执行了onBeforeMounted');
    })
    onMounted(() => {
      console.log('执行了onMounted');
      
    })
  }
})
</script>