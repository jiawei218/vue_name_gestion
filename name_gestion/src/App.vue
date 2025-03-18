<script setup>

import GestionName from "@/components/GestionName.vue";
</script>

<template>
  <div class="app">
    <header class="header-content">
        <img alt="Vue logo" class="logo" src="./assets/logo.svg"  />
        <h1 class="title">Name List</h1>
    </header>

    <div class="main">
      <GestionName />
    </div>

    <footer class="footer">
       <h1 class="welcome">Welcome to my first vue app !</h1>
    </footer>

  </div>
</template>

<style >
.app {
  min-width: 40vw;
}
/* Header  */
.header-content {
  background-color: honeydew;
  padding: 5px;
  display: flex;
  align-items: center;
  gap: 20px;

}

/* Main */
.main{
  margin: 20px auto;
  padding: 20px;
  background: white;
  display: flex;
}

/* Footer */
.footer {
  background: honeydew;
  padding: 5px;
  text-align: center;
  font-size: 8px;
  color: gray;
}

.title {
  margin: 0;
  font-size: 25px;
  color: #2c3e50;
}

.logo {
  width: 40px;
  height: 40px;
}
</style>
