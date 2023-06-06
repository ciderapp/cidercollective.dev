<template>
  <main>
    <div id="scrolldiv"></div>
    <div id="content1">
      <div id="welcome">
        <img src="../assets/logo.webp" alt="Cider Logo" id="logo">
        <h1 id="title">Cider Collective</h1>
        <h5 id="slogan" class="hide">A bridge, not a barrier</h5>
      </div>
    </div>
    <div id="content2">
      <div id="about">
        <h1>About Us</h1>
        <p>Born from the humble beginnings of an indie project christened as Apple Music Electron, we dared to dream, to defy, and to innovate. Our initial vision? To breathe life into an open-source client for Apple Music - one that was not shackled by Apple's constrained ecosystem, offering the breath of freedom users so rightly deserved. Over time, our aspirations grew and metamorphosed into a bigger and bolder endeavor - the birth of Cider.</p>
      </div>
      <div id="projects">
        <h1>Projects</h1>
        <div id="projects-grid">
          <Project image="ciderproject.png">
            <h4>Apple Music Electron</h4>
          </Project>
          <Project image="ciderproject.png">
            <h4>Cider</h4>
          </Project>
          <Project image="ciderproject.png">
            <h4>Cider 2</h4>
          </Project>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import {defineComponent} from 'vue'
import Project from "@/components/Project.vue";

export default defineComponent({
  name: "Home",
  components: {Project},
  created () {
    window.addEventListener('scroll', this.handleScroll);
  },
  unmounted () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll(e) {
      let viewHeight = window.innerHeight;

      if (window.scrollY > viewHeight / 2) {
        document.getElementById("logo").classList.add("hide");
        document.getElementById("logo").style.height = "0px";
        document.getElementById("logo").style.width = "0px";
      } else {
        document.getElementById("logo").classList.remove("hide");
        document.getElementById("logo").style.height = "200px";
        document.getElementById("logo").style.width = "200px";
      }

      if (window.scrollY > viewHeight) {
        document.getElementById("slogan").classList.remove("hide");
      } else {
        document.getElementById("slogan").classList.add("hide");
      }

      if (window.scrollY > viewHeight * 2) {
        document.getElementById("content1").style.position = "absolute";
        document.getElementById("content1").style.top = viewHeight * 2 + "px";
      } else {
        document.getElementById("content1").style.position = "fixed";
        document.getElementById("content1").style.top = "0px";
      }
    }
  }
})
</script>

<style lang="scss" scoped>
#scrolldiv {
  height: 600vh;
}

#content1 {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  font-family: Mona Sans,Mona Sans Header Fallback,-apple-system,BlinkMacSystemFont,Segoe UI,Helvetica,Arial,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol;
  #welcome {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    color: white;
    font-size: 1.5rem;
    transition: all 0.5s ease;
    #logo {
      width: 200px;
      transition: all 0.5s ease;
    }
    #title {
      font-weight: bolder;
      transition: all 0.5s ease;
    }
    #slogan {
      font-weight: normal;
      transition: all 0.5s ease;
      margin: 0;
    }
  }
}

#content2 {
  position: absolute;
  top: 300vh;
  width: 100vw;
  height: 100vh;
  font-family: Mona Sans,Mona Sans Header Fallback,-apple-system,BlinkMacSystemFont,Segoe UI,Helvetica,Arial,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol;
  color: white;
  #about {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    font-size: 1.5rem;
    text-align: center;
    h1 {
      font-weight: bolder;
    }
    p {
      width: 50%;
      font-size: 1.3rem;
    }
    @media (max-width: 768px) {
      p {
        width: 90%;
      }
    }
  }
  #projects {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    font-size: 1.5rem;
    text-align: center;
    h1 {
      font-weight: bolder;
    }
    #projects-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-gap: 40px;
      width: 90%;
      margin-top: 20px;
      @media (max-width: 768px) {
        grid-template-columns: 1fr;
      }
    }
  }
}

.hide {
  opacity: 0;
}
</style>