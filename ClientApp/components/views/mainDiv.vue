<template>
<div class="main-container">
  <transition name="slideUpScale">
    <div class="main" v-if="mainCard">
            <!-- <main class="main " :style="{display: isCamera? 'none': 'flex'} "> -->
            <div class="card ">
              <div class="img ">
                <img src="../../assets/img/girl.png" alt="girl">
              </div>
              <div class="headings ">

                <h1>Rachael Warren</h1>
                <h3>
                  Fullstack Developer
                </h3>

              </div>
              <div class="message ">
                <p>Since Rachael is pretty much only working with CBRE, there isn't much chance for feedback, but working with
                  Rachael has been awesome! She's super knowledgeable, approachable and always willing to help - just a nice
                  person who does a great job. When I found out I'd be transferring away from CBRE, my first though was "but
                  then I won 't be able to work with Rachael anymore!"
                </p>
              </div>
              <div class="progress-line"></div>
            </div>
      </div>
  </transition>
  <transition name="slideRight">
        <div class="sidebar">
            <!-- <section :style="{width: isCamera?'100%':'20%'}" class="sidebar"> -->
            <img class="logo" src="../../assets/svg/logo.svg" alt="logo">
            <div v-if="!fullSideBar" class="camera">
              <img src="../../assets/img/man.png" alt="">
            </div>
            <div class="user-info">
              <img src="../../assets/img/man.png" alt="">
              <h3>Marcus Laurens</h3>
              <h4>Art Director</h4>
            </div>

            <div class="camera-logo">
              <a @click="openCamera" >
                <img src="../../assets/svg/facescan.svg" alt="">
              </a>
              <span class="scanner"></span>
            </div>
      </div>
  </transition>

</div>

</template>

<script>
// import sidebar from "./sidebar";
import anime from "animejs";
export default {
  data() {
    return { mainCard: true, fullSideBar: true };
  },
  methods: {
    openCamera() {
      const tl = TimelineLite();
      this.mainCard = !this.mainCard;
      this.fullSideBar = !this.fullSideBar;
    }
  },
  mounted() {
    setInterval(() => {
      anime({
        targets: ".card",
        translateY: [
          { value: -700, duration: 2000 },
          { value: 0, duration: 2000 }
        ],
        scale: [{ value: 0.5, duration: 2000 }, { value: 1, duration: 2000 }],
        // loop: true,
        // delay: 2000,
        easing: "easeInOutCubic"
      });
    }, 5000);
  }
};
</script>

<style>

</style>
