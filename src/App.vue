<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <a href="#about">
          About
        </a>
        <a href="#projects">
          Projects
        </a>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style lang="scss">
html {
  scroll-behavior: smooth;
}

body {
  background-color: rgb(22, 22, 22);
  margin: 0 !important;
}
</style>

<style lang="scss" scoped>
header {
  position: absolute;
  z-index: 100;
  width: 100vw;
  .wrapper {
    nav {
      display: flex;
      justify-content: flex-end;
      padding: 2rem;
      font-family: Mona Sans,Mona Sans Header Fallback,-apple-system,BlinkMacSystemFont,Segoe UI,Helvetica,Arial,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol;
      a {
        color: white;
        font-size: 1.4rem;
        margin-left: 1rem;
        transition: all 0.3s ease;
        text-decoration: underline rgb(255, 38, 84, 0) 2px wavy;
        text-underline-offset: -0.1rem;
        &:hover {
          text-decoration-color: rgb(255, 38, 84, 1);
          text-underline-offset: 0.3rem;
        }
      }
    }
  }
}
</style>
