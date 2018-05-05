<template>
  <div class="main-container">
    <div ref="mainDiv"  class="main">
      <div ref="card" class="card">
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
    </div>
<!-- SIDE BAR  -->
    <div ref="sidebarTwo"  class="sidebar">
      <img class="logo" src="../../assets/svg/logo.svg" alt="logo">
      <div  class="camera">
        <img ref="camera" src="../../assets/img/man.png" alt="">
      </div>
      <div class="user-info">
        <img src="../../assets/img/man.png" alt="">
        <h3>Marcus Laurens</h3>
        <h4>Art Director</h4>
      </div>

      <div class="camera-logo">
        <a @click="runCamera">
          <img src="../../assets/svg/facescan.svg" alt="">
        </a>
        <span v-if="! mainCard" class="scanner"></span>
      </div>
    </div>
    <a @click="cameraClosed" v-if="!mainCard" href="#" class="float">
      <i class="fas fa-arrow-left arrow-float"></i>
    </a>
  </div>
</template>

<script>
import anime from "animejs";
export default {
  data() {
    return { mainCard: true, fullSideBar: false };
  },
  methods: {
    runCamera() {
      this.mainCard = !this.mainCard;
      if (!this.mainCard) this.cameraOpen();
    },
    cameraOpen() {
      const vm = this;
      var seq = [
        {
          e: vm.$refs.mainDiv,
          p: { translateX: 1000, opacity: 0.1, scale: 0.5 },
          o: { duration: 1000 }
        },
        {
          e: vm.$refs.sidebarTwo,
          p: { width: "100%" },
          o: { duration: 1000, sequenceQueue: false }
        },
        {
          e: vm.$refs.camera,
          p: "transition.expandIn",
          // p: { scale: 1 },
          // p: "transition.bounceRightIn",
          o: { duration: 1200, delay: 300, sequenceQueue: false }
        }
      ];
      Velocity.RunSequence(seq);
    },
    cameraClosed() {
      const vm = this;
      const seq = [
        {
          e: vm.$refs.mainDiv,
          p: { translateX: 0, opacity: 1, scale: 1 },
          o: { duration: 1000 }
        },
        {
          e: vm.$refs.sidebarTwo,
          p: { width: "330px" },
          o: { duration: 1000, sequenceQueue: false }
        },
        {
          e: vm.$refs.camera,
          p: "transition.expandOut",
          // p: "transition.bounceRightOut",
          // p: { scale: 0 },
          o: { duration: 1000, sequenceQueue: false }
        }
      ];
      Velocity.RunSequence(seq);
    },
    slideCards() {
      const vm = this;
      const seq = [
        {
          e: vm.$refs.card,
          p: "transition.slideUpBigOut",
          // p: "transition.expandOut",
          o: { delay: 600, duration: 1000 }
        },
        {
          e: vm.$refs.card,
          p: "transition.expandIn",
          p: "transition.slideUpBigIn",
          o: { duration: 1000 }
        }
      ];
      Velocity.RunSequence(seq);
    }
  },
  mounted() {
    window.addEventListener("keypress", e => {
      if (e.keyCode === 32) {
        return this.runCamera();
      }
    });
    setInterval(() => {
      this.slideCards();
    }, 3000);
    // setInterval(() => {
    //   anime({
    //     targets: ".card",
    //     translateY: [
    //       { value: -1000, duration: 2000 },
    //       { value: 0, duration: 2000 }
    //     ],
    //     scale: [{ value: 0.5, duration: 2000 }, { value: 1, duration: 2000 }],
    //     easing: "easeInOutCirc"
    //   });
    // }, 2000);
  }
};
</script>

<style >
@import url("../../css/maniDiv.css");
</style>
