<template>
  <v-app class="bg">
    <v-app-bar
      :color="scrolledPastThreshold ? 'indigo darken-2' : 'blue lighten-5'"
      app
      flat
      min-height="80"
      :dark="scrolledPastThreshold"
    >
      <!-- Use v-app-bar-nav-icon for burger icon -->
      <v-app-bar-nav-icon
        v-if="isSmallScreen"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>

      <div class="d-flex align-center md:pl-6 pt-5 justify-center">
        <v-img
          alt="Logo"
          class="rounded-md w-28"
          contain
          src="./assets/jobstore_mobile_icon2.png"
          transition="scale-transition"
        />
      </div>

      <v-spacer></v-spacer>
      <div v-if="!isSmallScreen" class="pt-4 sr-only sm:sr-only md:not-sr-only">
        <v-btn text class="font-satoshi font-medium hover-blue"
          >Browse Jobs</v-btn
        >
        <v-btn text class="font-satoshi font-medium hover-blue">
          Companies</v-btn
        >
        <v-btn text class="font-satoshi font-medium hover-blue">
          Campus Hiring
        </v-btn>
        <v-btn text class="font-satoshi font-medium hover-blue"
          >Government Jobs
        </v-btn>
        <v-btn text class="font-satoshi font-medium hover-blue">News </v-btn>
        <v-btn text class="font-satoshi font-medium hover-blue"
          >Resources
        </v-btn>
        <v-btn text class="font-satoshi font-medium hover-blue"
          >Download App</v-btn
        >
      </div>
      <v-spacer></v-spacer>
      <div v-if="!isSmallScreen" class="pt-4 mr-6 sm:flex">
        <v-btn
          text
          style="text-transform: none"
          :class="{
            'bg-slate-100': true,
            'text-indigo-700': true,

            'rounded-md': true,
            'font-satoshi': true,
            'text-base': true,
            'drop-shadow-md': true,
            'mr-2': true,
          }"
        >
          Sign In
        </v-btn>
        <v-btn
          text
          style="text-transform: none"
          :class="{
            'bg-indigo-700': !scrolledPastThreshold,
            'bg-blue-200': scrolledPastThreshold,
            'text-slate-50': !scrolledPastThreshold,
            'text-indigo-700': scrolledPastThreshold,
            'rounded-md': true,
            'font-satoshi': true,
            'text-base': true,
            'drop-shadow-md': true,
          }"
        >
          Sign Up
        </v-btn>
      </div>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>

    <!-- Drawer for small screens -->
    <v-navigation-drawer v-if="isSmallScreen" v-model="drawer" app>
      <!-- Your drawer content -->
    </v-navigation-drawer>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",

  data() {
    return {
      scrolledPastThreshold: false,
      scrollThreshold: 500, // Change this value to your desired scroll position
      drawer: false,
      isSmallScreen: false,
    };
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
    this.handleResize();
    window.addEventListener("resize", this.handleResize);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleScroll() {
      this.scrolledPastThreshold = window.scrollY >= this.scrollThreshold;
    },
    handleResize() {
      this.isSmallScreen = window.innerWidth < 800;
    },
  },
});
</script>
<style scoped>
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";

.bg {
  background-color: #e3f2fd;
}
.v-app-bar {
  background-color: #2663dd;
}
.hover-blue:hover {
  color: blue !important;
}
.bg-light-blue {
  background-color: #c3fdff;
}
</style>
