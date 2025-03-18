<script setup>

import GestionName from "@/components/GestionName.vue";
</script>

<template>

<div class="header-content">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="50" height="50" />
    <h1 class="title">Name Gestion</h1>
</div>

  <div class="main">
    <GestionName />
  </div>

  <div class="footer">
     <h1 class="welcome">Welcome to my first vue app !</h1>
   </div>

</template>

<style scoped>

.header-content {
  display: flex;
  justify-content: flex-end;  /* 元素靠右 */
  align-items: center;        /* 垂直居中 */
  gap: 20px;                  /* 元素间距 */
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}
.title {
  font-size: 30px;
  color: #2c3e50;
  margin: 0;
}

.main {
  max-width: 800px;
  padding: 0 20px;
  display: flex;
  justify-content: center;  /* 水平居中 */
  align-items: center;
}

.footer {
  display: flex;
  justify-content: center;  /* 水平居中 */
  align-items: center;      /* 垂直居中 */
  height: 200px;

}
.welcome {
  font-size: 15px;
  color:gray;
}

</style>
