<template>
<!-- 这里我们将会传递一个方法点击灰色部分的时候关闭页面 --> 
  <div @click="clickChild" v-if="isoc" class="w_o_d">
     <!-- 将内容放到页面 -->
    <div class="o_d_d">{{content}}</div>
  </div>
</template>

<script setup>
if (process.client) {
      window.alert("得到了浏览器对象")
      window.document.getElementById("id")
}
// 父传子
const props = defineProps({
  //子组件接收父组件传递过来的值
  content: "",
});
    let content =ref()
    content._value= props.content;
//   子传父
let isoc=ref(true)
const emit = defineEmits(['clickChild'])
const clickChild=()=>{
  let param={
    content:()=>{
        // 当点击灰色是关闭页面
        isoc.value=false;
    }
  }
  //传递给父组件
  emit('clickChild',param)
}
</script>
<script>
</script>

<style lang="scss" scoped>
.w_o_d {
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  position: fixed;
  .o_d_d {
    color: #fff;
  }
}
</style>