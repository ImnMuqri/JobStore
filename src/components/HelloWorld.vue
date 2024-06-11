<template>
  <div class="pt-12" style="width: 100%">
    <v-card class="h-full pt-10" color="#E3F2FD" elevation="0">
      <v-row class="mb-10" no-gutters>
        <v-col class="d-flex justify-center align-center">
          <div class="ml-4 md:ml-10 sm:mt-0">
            <v-row>
              <v-col>
                <h1
                  class="text-6xl sm:text-5xl md:text-7xl font-satoshi font-medium text-slate-800"
                >
                  Better Job,
                </h1>
                <h1
                  class="text-6xl sm:text-5xl md:text-7xl font-satoshi font-medium text-blue-800"
                >
                  Better Me
                </h1>
              </v-col>
            </v-row>
            <v-row justify="center" align="center">
              <v-col
                class="flex flex-col sm:flex-col md:flex-row md:space-x-2 justify-center items-center"
              >
                <v-text-field
                  outlined
                  hide-details
                  placeholder="Search Job Or Company Name"
                  class="rounded-lg bg-slate-100 w-full sm:w-76 mb-2 sm:mb-0 md:w-96 md:mb-0 md:mr-4"
                ></v-text-field>
                <v-btn
                  hide-details
                  text
                  height="35"
                  style="text-transform: none"
                  color="white"
                  class="bg-indigo-500 rounded-md text-base font-satoshi drop-shadow-md w-full sm:w-72 md:w-28"
                >
                  Find Jobs
                </v-btn>
              </v-col>
            </v-row>
          </div>
        </v-col>
        <v-col class="sr-only sm:not-sr-only">
          <v-img
            class="shrink w-20 sm:w-80 md:w-full lg:max-w-[650px]"
            contain
            src="../assets/GirlHP.png"
            transition="scale-transition"
          />
        </v-col>
      </v-row>
      <v-row class="mb-2 sr-only sm:not-sr-only">
        <v-col class="ml-1 mr-1 sm:ml-10 md:ml-24 sm:mr-10 md:mr-24">
          <div class="p-2 sm:pl-10 sm:pr-10 md:pl-10 md:pr-10">
            <v-card
              color="indigo darken-1"
              class="w-full h-20 sm:h-28 md:h-40 p-6 rounded-lg"
            >
              <v-row>
                <div class="flex space-x-4">
                  <v-col>
                    <v-img
                      contain
                      src="../assets/mycareerfair_logo.png"
                      class="ml-6 w-28 sm:w-34 md:w-96"
                    />
                  </v-col>
                  <v-col>
                    <div class="pl-3">
                      <p
                        class="text-xs sm:text-xs md:text-xl font-satoshi font-black gradient-text-yellow"
                      >
                        <span>26 - 27 OCTOBER 2024</span><br />
                        <span> 10AM - 6PM</span>
                      </p>
                    </div>
                  </v-col>
                  <v-col class="sr-only sm:not-sr-only">
                    <div class="pt-2">
                      <p
                        class="text-xs sm:text-sm md:text-lg font-satoshi text-white font-semibold"
                        ref="countdown"
                      >
                        Countdown<br />
                        <span>{{ countdown }}</span>
                      </p>
                    </div>
                  </v-col>
                </div>
              </v-row>
            </v-card>
          </div>
        </v-col>
      </v-row>
    </v-card>
    <v-row class="mt-10 mb-6">
      <v-card class="w-full" flat>
        <v-col class="flex p-12">
          <v-col class="sr-only md:not-sr-only md:pt-4 md:pl-2">
            <v-card
              color="#E3F2FD"
              elevation="0"
              class="rounded-xl w-28 md:pt-6 md:pl-2 md:w-96 md:h-96"
            >
              <v-img
                contain
                src="../assets/JobImg.png"
                class="ml-6 w-80 md:w-96"
              />
            </v-card>
          </v-col>
          <v-col class="pt-6 justify-center w-32 md:w-1/2">
            <div class="w-full h-full">
              <p
                class="text-2xl sm:text-2xl md:text-4xl font-satoshi font-semibold mb-6"
              >
                Save time with job recommendations that match your interests
              </p>
              <v-btn
                text
                height="45"
                style="text-transform: none"
                color="white"
                class="bg-indigo-700 rounded-lg text-base font-satoshi drop-shadow-md"
              >
                Explore Jobs >>
              </v-btn>
              <div
                class="overflow-x-scroll mt-6 h-full"
                style="scrollbar-width: none"
              >
                <div class="flex">
                  <div v-for="(JobItem, index) in Jobs" :key="index">
                    <v-card
                      class="drop-shadow-lg w-60 sm:w-96 m-3"
                      elevation="0"
                      style="border: 1px solid #ccc"
                    >
                      <div class="flex justify-between items-center">
                        <v-card-title
                          class="text-lg md:text-xl font-satoshi font-semibold"
                          style="white-space: normal; word-break: break-word"
                        >
                          {{ JobItem.Position }}
                        </v-card-title>
                      </div>
                      <div class="text-left pl-3">
                        <v-chip outlined color="orange">{{
                          JobItem.Location
                        }}</v-chip>
                      </div>
                      <div class="pl-2 pr-2">
                        <v-card-text>
                          <p
                            color="secondary"
                            class="text-base font-bold text-blue-600"
                          >
                            {{ JobItem.Company }}
                          </p>
                          <div class="flex space-between justify-between">
                            <p
                              class="font-satoshi text-base md:text-lg font-semibold text-green-600"
                            >
                              {{ JobItem.SalaryRange }}
                            </p>
                            <v-btn
                              dense
                              depressed
                              color="blue lighten-1"
                              dark
                              class="font-satoshi rounded-full"
                              style="text-transform: none"
                            >
                              View Job
                            </v-btn>
                          </div>
                        </v-card-text>
                      </div>
                    </v-card>
                  </div>
                </div>
              </div>
            </div>
          </v-col>
          <v-col cols="2" class="sr-only md:not-sr-only">
            <div class="mt-14 ml-2 flex align-center" style="height: 100%">
              <v-btn
                @click="scrollToNextJob"
                icon
                fab
                color="primary"
                class="bg-blue-50"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  width="24"
                  height="24"
                  color="#5B3DF6"
                  fill="none"
                >
                  <path
                    d="M9.00005 6C9.00005 6 15 10.4189 15 12C15 13.5812 9 18 9 18"
                    stroke="currentColor"
                    stroke-width="1.5"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </v-btn>
            </div>
          </v-col>
        </v-col>
      </v-card>
    </v-row>

    <v-row
      ><v-col class="md:pt-4 mb-10">
        <v-card
          elevation="0"
          color="#E3F2FD"
          class="mb-6 pl-5 md:pl-20 w-full md:pr-10 md:pr-16"
        >
          <v-col class="">
            <v-card-title
              class="text-2xl sm:text-3xl md:text-4xl font-satoshi font-semibold md:pl-10"
              style="white-space: normal; word-break: break-word"
              >News & Article</v-card-title
            >
          </v-col>

          <v-row no-gutters
            ><v-col class="md:p-2">
              <v-row no-gutters>
                <v-col class="ml-10 mb-1 d-flex justify-end">
                  <v-btn
                    text
                    height="40"
                    style="text-transform: none"
                    color="blue darken-4"
                    class="rounded-lg font-satoshi drop-shadow-md underline"
                  >
                    Read More >>
                  </v-btn>
                </v-col>
              </v-row>
              <div class="flex h-full md:ml-10 space-x-4 overflow-x-auto">
                <div
                  v-for="(newsItem, index) in newsItems"
                  :key="index"
                  class="mb-6"
                >
                  <v-card
                    elevation="0"
                    class="w-48 md:w-96 h-72 md:h-full rounded-lg overflow-hidden drop-shadow-lg mb-4"
                  >
                    <v-responsive>
                      <v-img
                        :src="getImagePath(newsItem.image)"
                        :alt="newsItem.title"
                        class="object-cover sm:h-48 md:h-64"
                      />
                    </v-responsive>
                    <v-card-title
                      class="pt-4 text-base mb-6"
                      style="white-space: normal; word-break: break-word"
                    >
                      {{ newsItem.title }}
                    </v-card-title>
                    <v-card-subtitle class="absolute bottom-0 left-0 right-0">{{
                      newsItem.date
                    }}</v-card-subtitle>
                  </v-card>
                </div>
              </div></v-col
            ></v-row
          >
        </v-card></v-col
      ></v-row
    >

    <v-card color="indigo darken-2" class="h-30 md:h-56 w-full" flat>
      <div class="pt-1 pb-1 md:pt-6 md:pb-6">
        <v-row class="justify-center align-center md:pt-5">
          <v-col cols="5">
            <v-card-title
              class="text-base sm:text-2xl md:text-4xl text-white font-satoshi font-semibold"
              style="white-space: normal; word-break: break-word"
              transition="scale-transition"
            >
              Your favourite job seeking app is now available on
              mobile</v-card-title
            >
          </v-col>
          <v-col cols="3">
            <v-row class="justify-end">
              <div class="p-10 space-y-4">
                <v-img
                  contain
                  src="../assets/app-store.png"
                  class="ml-6 w-6 md:w-12"
                />
                <v-img
                  contain
                  src="../assets/game.png"
                  class="ml-6 w-6 md:w-12"
                />
              </div>
            </v-row>
          </v-col>
          <v-col cols="3">
            <v-img
              contain
              src="../assets/jobstore_mobile_icon.png"
              class="md:ml-6 rounded-full drop-shadow-lg w-20 md:w-44"
            />
          </v-col>
        </v-row>
      </div>
    </v-card>
    <v-card flat class="w-full">
      <div class="pt-6">
        <v-row class="justify-center align-center p-6">
          <div class="w-full flex flex-col sm:flex-row">
            <v-col cols="12" sm="4" class="d-flex justify-center">
              <div class="flex flex-col items-center">
                <v-img
                  contain
                  src="../assets/JobStoreLogo.png"
                  class="drop-shadow-lg w-40 md:w-80"
                />
                <v-select
                  :items="items"
                  v-model="selectedItem"
                  outlined
                  color="primary"
                  hide-details
                  class="w-80 sm:w-30 md:w-80"
                ></v-select>
              </div>
            </v-col>

            <v-col
              cols="12"
              sm="auto"
              class="flex flex-col items-start sm:items-center sm:flex-grow"
            >
              <p
                class="font-satoshi font-black text-xs sm:text-sm md:text-lg mb-2"
              >
                Jobseeker
              </p>
              <div v-for="(item, index) in Jobseeker" :key="index">
                <p
                  class="font-satoshi text-xs font-medium hover:text-blue-500 cursor-pointer"
                  style="
                    text-transform: none;
                    white-space: normal;
                    word-break: break-word;
                  "
                >
                  {{ item }}
                </p>
              </div>
            </v-col>

            <v-col
              cols="12"
              sm="auto"
              class="flex flex-col items-start sm:items-center sm:flex-grow"
            >
              <p
                class="font-satoshi font-black text-xs sm:text-sm md:text-lg mb-2"
              >
                Corporate
              </p>
              <div v-for="(item, index) in corporate" :key="index">
                <p
                  class="font-satoshi text-xs font-medium hover:text-blue-500 cursor-pointer"
                  style="
                    text-transform: none;
                    white-space: normal;
                    word-break: break-word;
                  "
                >
                  {{ item }}
                </p>
              </div>
            </v-col>

            <v-col
              cols="12"
              sm="auto"
              class="flex flex-col items-start sm:items-center sm:flex-grow"
            >
              <p
                class="font-satoshi font-black text-xs sm:text-sm md:text-lg mb-2"
              >
                About
              </p>
              <div v-for="(item, index) in about" :key="index">
                <p
                  class="font-satoshi text-xs font-medium hover:text-blue-500 cursor-pointer"
                  style="
                    text-transform: none;
                    white-space: normal;
                    word-break: break-word;
                  "
                >
                  {{ item }}
                </p>
              </div>
            </v-col>

            <v-col
              cols="12"
              sm="auto"
              class="flex flex-col items-start sm:items-center sm:flex-grow"
            >
              <p
                class="font-satoshi font-black text-xs sm:text-sm md:text-lg mb-2"
              >
                Resources
              </p>
              <div v-for="(item, index) in resources" :key="index">
                <p
                  class="font-satoshi text-xs font-medium hover:text-blue-500 cursor-pointer"
                  style="
                    text-transform: none;
                    white-space: normal;
                    word-break: break-word;
                  "
                >
                  {{ item }}
                </p>
              </div>
            </v-col>
          </div>
        </v-row>
      </div>
    </v-card>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class HelloWorld extends Vue {
  countdown = "";

  Jobs = [
    {
      Position: "Software Developer",
      SalaryRange: "RM 4000 - RM 6000",
      Company: "Discord Inc",
      Location: "Kuala Lumpur",
    },
    {
      Position: "Web Developer",
      SalaryRange: "RM 3500 - RM 5500",
      Company: "Google",
      Location: "Penang",
    },
    {
      Position: "Data Scientist",
      SalaryRange: "RM 4500 - RM 7000",
      Company: "Microsoft",
      Location: "Johor Bahru",
    },
    {
      Position: "UX/UI Designer",
      SalaryRange: "RM 3800 - RM 5800",
      Company: "Apple",
      Location: "Kota Kinabalu",
    },
    {
      Position: "Marketing Specialist",
      SalaryRange: "RM 3200 - RM 5000",
      Company: "Facebook",
      Location: "Kuantan",
    },
  ];

  newsItems = [
    {
      title: "Experts warn of WhatsApp upfront fee jobscam",
      date: "10.06.2024",
      image: "Experts-warn-of-WhatsApp-upfront-fee-job-scam.jpg",
    },
    {
      title: "Media women protest employment stagnation and inequality",
      date: "12.06.2024",
      image: "Media-women-protest-employment-stagnation-and-inequality.jpg",
    },
    {
      title: "Malaysian Workers Lead Global AI Adoption",
      date: "14.06.2024",
      image: "Malaysian-Workers-Lead-Global-AI-Adoption-scaled.jpg",
    },
    {
      title: "Dragon Boat Festival consumption will boost China’s economy",
      date: "15.06.2024",
      image: "Dragon-Boat-Festival-consumption-will-boost-Chinas-economy.jpg",
    },
  ];
  getImagePath(image: string) {
    return require(`../assets/${image}`);
  }

  selectedItem = "Jobstore Malaysia";
  items = ["Jobstore Malaysia", "Jobstore Indonesia", "Jobstore Singapore"];

  Jobseeker = [
    "Create Account",
    "Sign In",
    "Search Jobs",
    "Search Employers",
    "Featured Companies",
    "Government Jobs",
    "Working in Singapore",
    "My Career Fair",
    "Industry News",
  ];

  corporate = [
    "Create Account",
    "Product & Services",
    "Pricing & Plan",
    "Advertise Jobs",
    "Industry News",
    "Customer Support",
    "Contact Sales",
  ];

  about = [
    "About Us",
    "Mobile App",
    "FAQs",
    "Contact Support",
    "Careers @ Jobstore",
    "Blog",
    "Fulfillment Policy",
  ];

  resources = [
    "Career Guide",
    "Job Templates",
    "Employer Resources",
    "Terms of Service",
    "Privacy Policy",
    "Partnership Inquiries",
  ];
  scrollToNextJob() {
    // Get the container element that holds the job cards
    const container = this.$el.querySelector(
      ".overflow-x-scroll"
    ) as HTMLElement | null;

    if (container) {
      // Calculate the width of each job card including margins
      const cardWidth = (container.querySelector(".rounded-lg") as HTMLElement)
        .offsetWidth;

      // Calculate the current scroll position
      const currentScrollPosition = container.scrollLeft;

      // Calculate the total width of all job cards
      const totalWidth = container.scrollWidth;

      // Calculate the index of the next job card
      let nextCardIndex = Math.floor(
        (currentScrollPosition + container.offsetWidth) / cardWidth
      );

      // If reaching the end, wrap back to the first job
      if (nextCardIndex * cardWidth >= totalWidth - container.offsetWidth) {
        nextCardIndex = 0;
      }

      // Calculate the scroll position to scroll to the next card
      const scrollPosition = nextCardIndex * cardWidth;

      // Smoothly scroll to the next card
      container.scrollTo({
        left: scrollPosition,
        behavior: "smooth",
      });
    }
  }

  updateCountdown() {
    const targetDate = new Date("2024-10-26T10:00:00"); // October 26, 2024, 10:00 AM
    const now = new Date();

    const diff = targetDate.getTime() - now.getTime();
    if (diff <= 0) {
      this.countdown = "Event has started!";
    } else {
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor(
        (diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      );
      const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((diff % (1000 * 60)) / 1000);

      this.countdown = `${days} Days ${hours} Hours ${minutes} Minutes ${seconds} Seconds`;
    }
  }

  async created() {
    this.updateCountdown(); // Update the countdown immediately
    setInterval(() => {
      this.updateCountdown();
    }, 1000); // Update the countdown every second
  }
}
</script>

<style>
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";

.gradient-text-yellow {
  /* Create a gradient color for text */
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  /* Define your gradient color here */
  background-image: linear-gradient(45deg, #ffd700, #ffd300);
}

.overflow-x-auto::-webkit-scrollbar {
  display: none; /* Chrome, Safari */
}
.hover-blue:hover {
  color: blue !important;
}
</style>
