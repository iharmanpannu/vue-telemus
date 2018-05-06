<template>
    <div id="app" >
          <router-view></router-view>
    </div>
        <!-- <div class="row"> -->
            <!-- <div class="col-sm-3">
                <nav-menu params="route: route"></nav-menu>
            </div> -->
        <!-- </div> -->
</template>

<script>
import Vue from "vue";
import HomePage from "./home-page";

Vue.component("home-page", HomePage);

export default {
  data() {
    return {};
  }
};
</script>

<style>
:root {
  --darkestGray: #a2afb9;
  --darkGray: #e7eaed;
  --lightGray: #ecf0f3;
  --headings: #000000;
  --white: #fff;
  --green: #44ee7c;
}

html,
body {
  background: var(--darkGray);
}
.main-container {
  height: 100vh;
  width: 100vw;
  display: flex;
  position: relative;
  clear: left;
  margin-left: auto;
  margin-right: auto;
}
</style>