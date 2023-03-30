<template>
  <div>
    <p>{{ num }}</p>
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
    const num = 10
    return {
      num: num
    }
  }
})
</script>