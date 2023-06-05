<template>
  <main>
    <div class="welcome">
      <img src="../assets/logo.webp" alt="Cider Logo">
      <h1>Cider Collective</h1>
      <h5>A bridge, not a barrier</h5>
<!--      <h5>We're a development group focused to changing the direction of the music industry to be more directionalized towards the general community and the consumers of music themselves</h5>-->
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
  font-family: Mona Sans,Mona Sans Header Fallback,-apple-system,BlinkMacSystemFont,Segoe UI,Helvetica,Arial,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol;
  .welcome {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: white;
    font-size: 1.5rem;
    img {
      width: 200px;
    }
    h1 {
      font-weight: bolder;
    }
    h5 {
      font-weight: normal;
      margin: 0;
    }
  }
}
</style>