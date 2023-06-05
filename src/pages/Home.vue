<template>
  <main>
    <div class="welcome">
      <img src="../assets/logo.webp" alt="Cider Logo">
      <h1>Cider Collective</h1>
    </div>
  </main>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "Home"
})
</script>

<style lang="scss" scoped>
main {
  .welcome {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: calc(100vh - 100px);
    color: white;
    img {
      width: 200px;
    }
  }
}
</style>