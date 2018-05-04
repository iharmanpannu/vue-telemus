<template>
  <div class="main-container">

    <div  class="main">
      <!-- <main class="main " :style="{display: isCamera? 'none': 'flex'} "> -->
        <transition

  @enter="enter"
  @leave="leave"

 >
      <div v-if="mainCard" class="card">
        <div class="img">
          <img src="../../assets/img/girl.png" alt="girl">
        </div>
        <div class="headings ">

          <h1>Rachael Warren</h1>
          <h3>
            Fullstack Developer
          </h3>

        </div>
        <div class="message">
          <p>Since Rachael is pretty much only working with CBRE, there isn't much chance for feedback, but working with Rachael
            has been awesome! She's super knowledgeable, approachable and always willing to help - just a nice person who
            does a great job. When I found out I'd be transferring away from CBRE, my first though was "but then I won 't
            be able to work with Rachael anymore!"
          </p>
        </div>
        <div class="progress-line"></div>
      </div>
        </transition>
    </div>


  <transition
    @enter="enter"
  >
    <div  class="sidebar">
      <!-- <section :style="{width: isCamera?'100%':'20%'}" class="sidebar"> -->
      <img class="logo" src="../../assets/svg/logo.svg" alt="logo">
      <div v-if="fullSideBar" class="camera">
        <img src="../../assets/img/man.png" alt="">
      </div>
      <div class="user-info">
        <img src="../../assets/img/man.png" alt="">
        <h3>Marcus Laurens</h3>
        <h4>Art Director</h4>
      </div>

      <div class="camera-logo">
        <a @click="openCamera">
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
    return { mainCard: true, fullSideBar: false };
  },

  methods: {
    openCamera() {
      this.mainCard = !this.mainCard;
      this.fullSideBar = !this.fullSideBar;
    },
    beforeEnter: function(el) {
      Velocity(el, { display: "none" });
    },
    enter: function(el, done) {
      Velocity(
        el,
        { translateY: 0 },
        { display: "flex" },
        { duration: 800 },
        { complete: done }
      );
      // Velocity(el, { fontSize: "1em" });
    },
    leave: function(el, done) {
      Velocity(
        el,
        { translateX: -1000, display: "none" },
        [1, -0.79, 0.83, 0.67],
        {
          complete: done
        }
      );
    }
  },
  mounted() {
    // setInterval(() => {
    //   anime({
    //     targets: ".card",
    //     translateY: [
    //       { value: -1000, duration: 2000 },
    //       { value: 0, duration: 2000 }
    //     ],
    //     scale: [{ value: 0.5, duration: 2000 }, { value: 1, duration: 2000 }],
    //     // loop: true,
    //     // delay: 2000,
    //     easing: "easeInOutCirc"
    //   });
    // }, 5000);
  }
};
</script>

<style >
@import url("../../css/maniDiv.css");
</style>
