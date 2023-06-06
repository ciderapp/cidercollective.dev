<template>
  <div class="project">
    <img :src="'/' + image" alt="Project Image">
    <div class="details">
      <div class="bottom">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "Project",
  props: {
    image: String
  }
})
</script>

<style scoped lang="scss">
.project {
  position: relative;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 10px;
  }
  .details {
    float: left;
    position: absolute;
    left: 0;
    top: 0;
    z-index: 1000;
    width: 100%;
    height: 100%;
    .bottom {
position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      padding: 1rem;
      background-color: rgba(0, 0, 0, 0.5);
      border-bottom-left-radius: 10px;
      border-bottom-right-radius: 10px;
      transition: all 0.3s ease;
      opacity: 0;
      &:hover {
        opacity: 1;
      }
    }
  }
}
</style>