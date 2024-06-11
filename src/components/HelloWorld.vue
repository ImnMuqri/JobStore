<template>
  <v-container fluid>
    <v-card class="pt-5 sm:pt-10" color="#E3F2FD" elevation="0">
      <v-row class="mb-10 pt-5 sm:pt-10 h-2/3">
        <v-col
          class="d-flex justify-center items-center sm:items-end md:items-center"
        >
          <div class="md:ml-10 w-80 sm:w-80 text-center">
            <v-row>
              <v-col>
                <v-col class="w-full d-flex justify-center">
                  <v-img
                    v-if="
                      $vuetify.breakpoint.smOnly || $vuetify.breakpoint.xsOnly
                    "
                    class="shrink w-60 sm:w-0"
                    src="../assets/GirlHP.png"
                    transition="scale-transition"
                    contain
                  />
                </v-col>
                <h1
                  class="sm:pl-2 text-5xl sm:text-6xl md:text-6xl lg:text-6xl font-satoshi font-medium text-slate-800"
                >
                  Better Job,
                </h1>
                <h1
                  class="sm:pl-2 text-6xl sm:text-5xl md:text-6xl lg:text-6xl font-satoshi font-medium text-blue-800"
                >
                  Better Me
                </h1>
              </v-col>
            </v-row>
            <v-row justify="center" align="center">
              <v-col
                class="flex flex-col sm:flex-col md:flex-col lg:flex-row lg:space-x-2 justify-center items-center"
              >
                <v-text-field
                  outlined
                  hide-details
                  height="20"
                  placeholder="Search Job Or Company Name"
                  class="rounded-lg bg-slate-100 w-full sm:w-50 mb-3 sm:mb-0 md:w-96 md:mb-0 md:mr-4"
                ></v-text-field>
                <v-btn
                  hide-details
                  text
                  height="50"
                  style="text-transform: none"
                  color="white"
                  class="bg-indigo-500 rounded-lg text-base font-satoshi drop-shadow-md w-full sm:w-full md:w-full lg:w-28 mt-0 sm:mt-4 mb-3"
                >
                  Find Jobs
                </v-btn>
                <span v-show="$vuetify.breakpoint.xsOnly" class="mb-2">
                  Or</span
                >
                <v-btn
                  v-show="$vuetify.breakpoint.xsOnly"
                  text
                  height="45"
                  style="text-transform: none"
                  class="bg-blue-200 text-indigo-600 rounded-lg text-base font-satoshi drop-shadow-sm w-full mb-4"
                >
                  Sign Up
                </v-btn>
                <v-btn
                  v-show="$vuetify.breakpoint.xsOnly"
                  text
                  height="45"
                  style="text-transform: none"
                  class="bg-slate-50 rounded-lg text-base font-satoshi drop-shadow-sm w-full"
                >
                  Sign In
                </v-btn>
              </v-col>
            </v-row>
          </div>

          <v-img
            class="shrink w-full sm:w-72 md:w-100 lg:w-2/5 hidden sm:block"
            src="../assets/GirlHP.png"
            transition="scale-transition"
          />
        </v-col>
      </v-row>
      <v-row class="mb-2 sr-only sm:not-sr-only">
        <v-col class="ml-1 mr-1 sm:ml-10 md:ml-24 sm:mr-10 md:mr-24">
          <div class="p-2 sm:pl-2 sm:pr-2 md:pl-3 md:pr-3">
            <v-card
              color="indigo darken-1"
              class="w-full h-20 sm:h-28 md:h-44 lg:h-44 p-6 rounded-lg"
            >
              <v-row>
                <div class="flex space-x-4">
                  <v-col>
                    <v-img
                      contain
                      src="../assets/mycareerfair_logo.png"
                      class="ml-6 w-36 md:w-64 lg:w-80"
                    />
                  </v-col>
                  <v-col>
                    <div class="pl-3">
                      <p
                        class="text-xs sm:text-xs md:text-xl lg:text-2xl font-satoshi font-black gradient-text-yellow"
                      >
                        <span>26 - 27 OCTOBER 2024</span><br />
                        <span> 10AM - 6PM</span>
                      </p>
                    </div>
                  </v-col>
                  <v-col class="sr-only sm:not-sr-only">
                    <div class="pt-2">
                      <p
                        class="text-xs sm:text-sm md:text-xl lg:text-2xl font-satoshi text-white font-semibold"
                        ref="countdown"
                      >
                        Countdown:<br />
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
    <v-card class="mb-4">
      <v-row>
        <v-card class="w-full" flat>
          <v-col class="flex pl-6 pr-6 pt-6 justify-start">
            <v-col
              cols="3"
              class="md:pt-4 lg:pl-2 md:w-1/3 d-flex justify-end sr-only sm:sr-only lg:not-sr-only"
            >
              <v-card
                color="#E3F2FD"
                elevation="0"
                class="rounded-xl lg:pt-6 lg:pl-2 g:w-96 lg:h-full"
              >
                <v-img contain src="../assets/JobImg.png" class="ml-6 w-full" />
              </v-card>
            </v-col>
            <v-col class="pt-6 md:pl-10 justify-center w-32 md:w-2/3">
              <p
                class="text-2xl sm:text-2xl md:text-4xl font-satoshi font-semibold mb-2"
              >
                Save your time with job recommendations that match your
                interests
              </p>
              <p
                class="text-xl sm:text-sm md:text-xl font-satoshi font-medium text-slate-500 mb-6"
              >
                Discover tailored job suggestions aligned with your skills and
                preferences, simplify your search, and seize exciting career
                opportunities faster with personalized recommendations from our
                platform.
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
            </v-col>
          </v-col>
          <v-col class="pl-6 pr-6">
            <div class="overflow-x-scroll h-full" style="scrollbar-width: none">
              <p class="text-lg font-satoshi font-medium pl-4 lg:pt-2">
                #TrendingJobs
              </p>
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
          </v-col>
        </v-card>
      </v-row>
    </v-card>

    <v-card>
      <v-row>
        <v-card
          elevation="0"
          color="#E3F2FD"
          class="mb-6 pl-1 md:pl-20 w-full md:pr-10 md:pr-16"
        >
          <v-col class="pl-6">
            <v-card-title
              class="text-3xl sm:text-4xl md:text-4xl font-satoshi font-semibold text-blue-800"
              style="white-space: normal; word-break: break-word"
              >News & Article</v-card-title
            >
            <v-col class="d-flex justify-end">
              <v-btn
                text
                height="40"
                style="text-transform: none"
                color="blue darken-4"
                class="rounded-lg font-satoshi drop-shadow-md underline"
              >
                Read More >>
              </v-btn> </v-col
            ><v-row class="md:p-2">
              <div class="flex h-30 md:ml-6 space-x-4 overflow-x-auto">
                <div
                  v-for="(newsItem, index) in newsItems"
                  :key="index"
                  class="mb-6 w-fit"
                >
                  <v-card
                    elevation="0"
                    class="w-48 lg:w-64 h-60 sm:h-50 md:h-72 lg:h-full rounded-lg overflow-hidden drop-shadow-lg mb-4"
                  >
                    <v-responsive>
                      <v-img
                        :src="getImagePath(newsItem.image)"
                        :alt="newsItem.title"
                        class="object-cover sm:h-32 md:h-40 lg:h-40"
                      />
                    </v-responsive>
                    <v-card-title
                      class="pt-4 text-xs mb-6 sm:text-sm md:text-base lg:text-base"
                      style="white-space: normal; word-break: break-word"
                    >
                      {{ newsItem.title }}
                    </v-card-title>
                    <v-card-subtitle class="absolute bottom-0 left-0 right-0">{{
                      newsItem.date
                    }}</v-card-subtitle>
                  </v-card>
                </div>
              </div></v-row
            >
          </v-col>
        </v-card></v-row
      >
    </v-card>
    <v-card class="mb-4">
      <v-row>
        <v-card color="indigo darken-2" class="h-30 md:h-56 w-full">
          <div class="pt-1 pb-1 md:pt-6 md:pb-6">
            <v-row class="justify-center align-center md:pt-5">
              <v-col cols="5">
                <v-card-title
                  class="text-base sm:text-2xl md:text-4xl text-white font-satoshi font-semibold"
                  style="white-space: normal; word-break: break-word"
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
                  class="md:ml-6 rounded-full drop-shadow-lg w-20 md:w-40 sm:w-28"
                />
              </v-col>
            </v-row>
          </div>
        </v-card>
      </v-row>
    </v-card>
    <v-card class="mb-4">
      <v-row>
        <v-card flat class="w-full">
          <div class="pt-6">
            <v-row class="justify-center align-center p-6">
              <div class="w-full flex flex-col sm:flex-row md:flex-row">
                <v-col cols="12" sm="4" class="d-flex justify-center">
                  <div class="flex flex-col items-center">
                    <v-img
                      contain
                      src="../assets/JobStoreLogo.png"
                      class="drop-shadow-lg w-40 md:w-72"
                    />
                    <v-select
                      :items="items"
                      v-model="selectedItem"
                      outlined
                      dense
                      color="primary"
                      hide-details
                      class="w-80 sm:w-30 md:w-80"
                    ></v-select>
                  </div>
                </v-col>

                <v-col
                  cols="16"
                  sm="auto"
                  class="flex flex-col items-start sm:items-start sm:flex-grow"
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
                  class="flex flex-col items-start sm:items-start sm:flex-grow"
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
                  class="flex flex-col items-start sm:items-start sm:flex-grow"
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
                  class="flex flex-col items-start sm:items-start sm:flex-grow"
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
      </v-row>
    </v-card>
  </v-container>
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
      date: "9.06.2024",
      image: "Experts-warn-of-WhatsApp-upfront-fee-job-scam.jpg",
    },
    {
      title: "Media women protest employment stagnation and inequality",
      date: "10.06.2024",
      image: "Media-women-protest-employment-stagnation-and-inequality.jpg",
    },
    {
      title: "Malaysian Workers Lead Global AI Adoption",
      date: "10.06.2024",
      image: "Malaysian-Workers-Lead-Global-AI-Adoption-scaled.jpg",
    },
    {
      title: "Dragon Boat Festival consumption will boost China’s economy",
      date: "11.06.2024",
      image: "Dragon-Boat-Festival-consumption-will-boost-Chinas-economy.jpg",
    },
    {
      title:
        "Amir Hamzah: Malaysia's economic transformation momentum to accelerate this year",
      date: "11.06.2024",
      image: "Amir.jpg",
    },
    {
      title:
        "'Malaysia has made progress in 2 out of 7 Johor-Singapore Special Economic Zone initiatives'",
      date: "11.06.2024",
      image: "Sing.jpg",
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
.v-application p {
  margin-bottom: 0 !important; /* Override the margin */
}
</style>
