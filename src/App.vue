<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style lang="scss">
body {
  background-color: rgb(22, 22, 22);
  margin: 0 !important;
}
</style>

<style lang="scss" scoped>
header {
  .wrapper {
    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 100px;
    }
  }
}
</style>
