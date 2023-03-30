<template>
  <!-- <div class="home"> -->
    <p ref="op">{{ objRet.num }}</p>
  <!-- </div> -->
</template>

<script lang='ts' setup>
// setup语法糖加上后，视为在setup中
import {reactive, toRefs} from 'vue';

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
  
</style>