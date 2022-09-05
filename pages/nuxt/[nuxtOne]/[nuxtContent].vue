<template>
  <div>
    <!-- 用事件传入 -->
    <walert :content="content" @clickChild="clickEven"></walert>
        <img src="../../../public/1.png"/>
  </div>
</template>
<script setup>
import walert from "..//../../components/wAlert.vue";
const router=useRouter();
console.log(router.currentRoute._rawValue.params)
// 传入的内容  夫传子
let content=ref("从父组件传到子组件")

// 子传父
const clickEven=(val)=>{
    // 执行方法关闭弹窗
    val.content()
}
</script>
<style>
</style>