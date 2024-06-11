<template>
  <v-app class="bg overflow-x-hidden">
    <v-app-bar
      :color="scrolledPastThreshold ? 'indigo darken-2' : 'blue lighten-5'"
      app
      flat
      min-height="80"
      :dark="scrolledPastThreshold"
    >
      <div class="d-flex align-center pt-5 justify-center">
        <v-app-bar-nav-icon
          v-if="isSmallScreen"
          @click.stop="drawer = !drawer"
        ></v-app-bar-nav-icon>
      </div>

      <div class="d-flex align-center md:pl-6 pt-5 justify-center mx-auto">
        <v-img
          alt="Logo"
          class="rounded-md w-20 sm:w-28"
          contain
          src="./assets/jobstore_mobile_icon2.png"
          transition="scale-transition"
        />
      </div>

      <v-spacer></v-spacer>
      <div
        v-if="!isSmallScreen"
        class="pt-4 sr-only sm:sr-only md:sr-only lg:not-sr-only"
      >
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
    <v-navigation-drawer
      v-model="drawer"
      v-if="isSmallScreen"
      absolute
      left
      temporary
      width="100%"
      class="bg-blue-900"
      style="overflow-y: hidden"
    >
      <v-container>
        <v-row align="center" justify="center">
          <v-col cols="12" class="text-center">
            <v-list nav dense class="pt-12">
              <v-list-item-group
                v-model="group"
                active-class="deep-purple--text text--accent-4"
              >
                <v-list-item v-for="(item, index) in items" :key="index">
                  <v-list-item-subtitle
                    class="white--text font-satoshi text-xl h-6"
                    style="font-size: 18px; font-family: 'Satoshi', sans-serif"
                  >
                    {{ item.title }}
                  </v-list-item-subtitle>
                </v-list-item>
              </v-list-item-group>
            </v-list>
            <v-btn
              @click="drawer = false"
              icon
              fab
              color="error"
              class="bg-blue-50 mt-6"
            >
              <v-icon>mdi-close</v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
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
      scrollThreshold: 400, // Change this value to your desired scroll position
      drawer: false,
      isSmallScreen: false,
      group: null,

      items: [
        { title: "Browse Jobs", icon: "mdi-view-dashboard" },
        { title: "Companies", icon: "mdi-image" },
        { title: "Campus Hiring", icon: "mdi-help-box" },
        { title: "Government Jobs", icon: "mdi-view-dashboard" },
        { title: "News", icon: "mdi-image" },
        { title: "Resources", icon: "mdi-help-box" },
        { title: "Download App", icon: "mdi-view-dashboard" },
      ],
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
