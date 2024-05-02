<template>
  <div class="full-screen-background">
    <Header v-show="isHeader"></Header>
    <router-view></router-view>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import { defineComponent } from "vue";
export default defineComponent({
  name: "App",
});
</script>
<script setup>
import { computed } from "vue";
import { useRoute } from "vue-router";
const route = useRoute(); // 路由信息对象
// 判断是否显示header组件
const isHeader = computed(() => {
  return (
    route.name !== "Login" &&
    route.name !== "Register" &&
    route.name !== "addNews"
  );
});
</script>

<style lang="less" scoped>
.full-screen-background {
  background-image: url("https://s21.ax1x.com/2024/05/03/pkkhOCd.jpg");
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
  width: 100%;
  height: 100vh;
}
</style>
