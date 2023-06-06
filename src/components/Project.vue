<template>
  <a class="project" :href="link" target="_blank">
    <img :src="'/' + image" alt="Project Image">
    <div class="details">
      <div class="bottom">
        <slot></slot>
      </div>
    </div>
  </a>
</template>

<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "Project",
  props: {
    image: String,
    link: String
  }
})
</script>

<style scoped lang="scss">
.project {
  position: relative;
  cursor: pointer;
  color: white;
  text-decoration: none;
  transition: all 0.5s ease;
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
    background-image: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
    transition: all 0.5s ease;
    opacity: 0;
    .bottom {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      border-bottom-left-radius: 10px;
      border-bottom-right-radius: 10px;
      transition: all 0.5s ease;
      opacity: 0;
      text-align: center;
    }
  }
  // On hover change the opacity of the details
  body.hasHover &:hover {
    transform: scale(1.05);
    .details {
      opacity: 1;
      .bottom {
        opacity: 1;
      }
    }
  }
}
</style>