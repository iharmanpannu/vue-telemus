<template>
  <div class="main-container">
    <div class="main" v-if="mainCard" >
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
          <p>Since Rachael is pretty much only working with CBRE, there isn't much chance for feedback, but working with Rachael
            has been awesome! She's super knowledgeable, approachable and always willing to help - just a nice person who
            does a great job. When I found out I'd be transferring away from CBRE, my first though was "but then I won 't
            be able to work with Rachael anymore!"
          </p>
        </div>
        <div class="progress-line"></div>
      </div>
    </div>
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
        <a @click="openCamera">
          <img src="../../assets/svg/facescan.svg" alt="">
        </a>
        <span class="scanner"></span>
      </div>
    </div>
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
      this.mainCard = !this.mainCard;
      // if (this.mainCard) {
      //   return this.slideOut();
      // } else {
      //   return this.slideIn() && (this.mainCard = true);
      // }
    },
    slideOut() {
      return anime({
        targets: ".main",
        translateX: { value: -1000, duration: 2000 },
        easing: "easeInOutCirc"
      });
    },
    slideIn() {
      return anime({
        targets: ".main",
        translateX: { value: -1000, duration: 2000 },
        easing: "easeInOutCirc"
      });
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

<style>
/* MAIN DIV STYLE  */
.main {
  padding: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  justify-content: space-evenly;
}

.main .card {
  height: 100%;
  position: relative;
  background: var(--white);
  text-align: center;
  padding: 3rem;
  background-color: var(--white);
  box-shadow: 0 44px 88px 0 rgba(0, 0, 0, 0.13);
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.main img {
  border-radius: 50%;
  width: 180px;
}
.main.card h1 {
  font-size: 2rem;
}
.main .card h3 {
  font-size: 1.2rem;
  text-transform: uppercase;
  opacity: 0.5;
  margin-bottom: 1rem;
}
.main.card p {
  line-height: 2rem;
  font-size: 1.2rem;
  font-weight: 400;
}

/* CARD 2 STYLE  */

/* SCREEN AFTER CAMERA REQUEST APPROVED  */
.card-2 {
  position: relative;
  background: var(--white);
  text-align: center;
  padding: 3rem;
  background-color: var(--white);
  box-shadow: 0 44px 88px 0 rgba(0, 0, 0, 0.13);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.card-2 .quote {
  color: var(--darkGray);
  font-size: 6rem;
  font-weight: 600;
}
.card-2-info {
  margin-top: 4rem;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  /* padding: 0 2rem; */
}
.card-2-info > div {
  margin: 0 1rem;
  text-align: left;
}
.card-2-user-info > * {
  margin-bottom: 0.7rem;
}
.card-2-user-info img {
  width: 100px;
}
.card-2-user-info h3 {
  font-size: 2.8rem;
}
.card-2-user-info h4 {
  font-size: 1.5rem;
  opacity: 0.5;
  text-transform: uppercase;
}

/* SIDE BAR STYLES  */

.sidebar {
  padding: 3rem 2rem;
  display: flex;
  /* width: 300px; */
  height: 100%;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  background-color: var(--lightGray);
  box-shadow: 0 0 81px 0 rgba(0, 0, 0, 0.08);
}

.sidebar .logo {
  /* opacity: 0.9; */
  padding: 1.8rem;
}
.camera img {
  transform: scale(0);
  border-radius: 50%;
  width: 400px;
  border: 20px solid var(--white);
  box-shadow: 0 0 40px 0 rgba(0, 0, 0, 0.1);
}
.camera-logo {
  position: relative;
}
.sidebar .camera-logo img {
  width: 75px;
  height: 100px;
  padding: 0.2rem;
}

/* USER INFORMATION  */
.user-info {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
}
.user-info img {
  border-radius: 50%;
  width: 250px;
  box-shadow: 0 0 40px 0 rgba(0, 0, 0, 0.1);
  margin-bottom: 1rem;
}
.user-info h3 {
  margin-bottom: 0.5rem;
  font-weight: 600;
  font-size: 1.5rem;
}
.user-info h4 {
  opacity: 0.5;
  text-transform: uppercase;
}

/* PAUSED STUFF */
.user-info {
  display: none;
}
.scanner {
  display: none;
}

.slideIn-enter-to {
  width: 100%;
}
/* MEDIA QUERY  */
@media (max-width: 90rem) {
  .main .card {
    padding: 6rem;
  }
  .main .card h1 {
    font-size: 3rem;
  }
  .main .card h3 {
    font-size: 1.5rem;
  }
  .main p {
    line-height: 2.3rem;
    font-size: 1.5rem;
  }
  /* CARD 2 STYLE  */
  .card-2-info img {
    width: 120px;
  }
}

/* WIDE SCREEN ANINAMATION  */
@media (min-width: 91rem) {
  .main {
    padding: 4rem;
  }

  .main .card {
    padding: 6rem;
    height: 100%;
  }

  .main .card h1 {
    font-size: 4rem;
  }
  .main .card h3 {
    font-size: 2.2rem;
    text-transform: uppercase;
    opacity: 0.5;
  }
  .main p {
    line-height: 3.5rem;
    padding: 0 9rem;
    font-size: 2.2rem;
    font-weight: 400;
  }
  .main .card img {
    width: 350px;
  }

  .camera img {
    width: 640px;
  }
  /* CARD 2  */
  .card-2 {
    padding: 6rem;
    height: 100%;
  }
  .card-2 img {
    width: 150px;
  }

  .card-2-user-info h3 {
    font-size: 3.5rem;
  }
  .card-2-user-info h4 {
    font-size: 1.8rem;
  }
}

/* PROGRESS LINE  */

.progress-line,
.progress-line:before {
  height: 3px;
  width: 100%;
  margin: 0;
}
.progress-line {
  margin-top: auto;
  justify-self: flex-end;
  align-self: flex-start;
}
.progress-line {
  background-color: var(--lightGray);
  display: -webkit-flex;
  display: flex;
  width: 100%;
  position: absolute;
  right: -0%;
  bottom: -0%;
}

.progress-line:before {
  background-color: var(--darkestGray);
  content: "";
  -webkit-animation: running-progress 2s cubic-bezier(0.4, 0, 0.2, 1) infinite;
  animation: running-progress 2s cubic-bezier(0.4, 0, 0.2, 1) infinite;
}
@-webkit-keyframes running-progress {
  0% {
    margin-left: 0px;
    margin-right: 100%;
  }
  50% {
    margin-left: 25%;
    margin-right: 0%;
  }
  100% {
    margin-left: 100%;
    margin-right: 0;
  }
}
@keyframes running-progress {
  0% {
    margin-left: 0px;
    margin-right: 100%;
  }
  50% {
    margin-left: 25%;
    margin-right: 0%;
  }
  100% {
    margin-left: 100%;
    margin-right: 0;
  }
}

/* SCANNING ANIMATION  */

.camera-logo span {
  position: absolute;
  left: 0;
  top: 10%;
  width: 100%;
  height: 5px;

  background-color: var(--green);
  z-index: 1;
  transform: translateY(135%);
  animation: move 0.8s cubic-bezier(0.15, 0.44, 0.76, 0.64);
  animation-iteration-count: infinite;
}
@keyframes move {
  0%,
  100% {
    transform: translateY(100%);
  }
  50% {
    transform: translateY(0%);
  }
  75% {
    transform: translateY(70px);
  }
}

/* .sidebar {
  width: 100%;
}
.main {
  display: none;
} */
/* .camera {
  display: none;
} */
</style>
