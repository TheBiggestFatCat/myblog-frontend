<template>
  <div class="home">
    
  </div>
</template>

<script lang='ts' setup>
import { reactive } from 'vue';

let obj = {
  num: 20
}
let objRet = reactive(obj)
console.log(objRet);
console.log(objRet.num);

return {
  objRet
}
</script>
 
<style lang="less" scoped>
.home {
  background-image: url(@/assets/pics/home1.jpg);
}
</style>