<template>
  <v-container>
    <v-row>
      <v-col class="text-center">
        <v-avatar size="160" class="mt-9">
          <img
            src="../assets/coby-yates-profile-pic.png"
            alt="Profile Picture of Coby Yates"
          />
        </v-avatar>
        <h2 class="display-1 my-5">Coby Yates</h2>
        <v-divider></v-divider>
        <v-row class="mt-12 ml-12">
          <v-col class="text-center">
            <h2 class="text-left font-weight-thin">LANGUAGES</h2>
            <div
              class="d-flex align-baseline "
              v-for="lang in langs"
              :key="lang"
            >
              <v-col class="mx-0 px-0" cols="2">
                <v-icon medium :color="lang.color" class="mr-4">{{
                  lang.icon
                }}</v-icon>
              </v-col>
              <v-col class="mx-0 px-0 pb-0 text-left" cols="10">
                <p class="mb-0">{{ lang.title }}</p>
              </v-col>
            </div>
          </v-col>
          <v-col class="text-center">
            <h2 class="text-left font-weight-thin">FRAMEWORKS</h2>
            <div
              class="d-flex align-baseline"
              v-for="framework in frameworks"
              :key="framework"
            >
              <v-col class="mx-0 px-0" cols="2">
                <v-icon medium :color="framework.color" class="mr-4">{{
                  framework.icon
                }}</v-icon>
              </v-col>
              <v-col class="mx-0 px-0 pb-0 text-left" cols="10">
                <p class="mb-0">{{ framework.title }}</p>
              </v-col>
            </div>
          </v-col>
          <v-col class="text-center">
            <h2 class="text-left font-weight-thin">SOFTWARE</h2>
            <div
              class="d-flex align-baseline"
              v-for="software in softwares"
              :key="software"
            >
              <v-col class="mx-0 px-0" cols="2">
                <v-icon medium :color="software.color" class="mr-4">{{
                  software.icon
                }}</v-icon>
              </v-col>
              <v-col class="mx-0 px-0 pb-0 text-left" cols="10">
                <p class="mb-0">{{ software.title }}</p>
              </v-col>
            </div>
          </v-col>
          <v-col class="text-center">
            <h2 class="text-left font-weight-thin">ADDITIONAL</h2>
            <div
              class="d-flex align-baseline"
              v-for="additional in additionals"
              :key="additional"
            >
              <v-col class="mx-0 px-0" cols="2">
                <v-icon medium :color="additional.color" class="mr-4">{{
                  additional.icon
                }}</v-icon>
              </v-col>
              <v-col class="mx-0 px-0 pb-0 text-left" cols="10">
                <p class="mb-0">{{ additional.title }}</p>
              </v-col>
            </div>
          </v-col>
        </v-row>
        <v-divider class="my-5"></v-divider>
        <v-row>
          <v-col>
            <h2 class="mb-10 font-weight-thin">EXPERIENCE WITH</h2>
            <div class="d-flex justify-space-between">
              <div
                v-for="experience in experiences"
                :key="experience"
                class="d-flex align-baseline"
              >
                <v-icon medium :color="experience.color" class="mr-4">
                  {{ experience.icon }}
                </v-icon>
                <p>{{ experience.title }}</p>
              </div>
            </div>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
    <v-divider class="my-5 ml-auto mr-auto" width="50%"></v-divider>
    <v-row class="mb-12">
      <v-col class="text-center">
        <h2 class="display-1 text-center font-weight-thin">My Work</h2>
        <v-card
          color="red lighten-4"
          height="100px"
          class="d-flex align-center justify-center black--text my-6 display-1"
          >This section is currently being developed</v-card
        >
        <!-- MY WORK -->
        <v-card flat tile class="mt-6">
          <v-window v-model="onboarding" vertical>
            <v-window-item v-for="project in projects" :key="project">
              <v-card :color="project.color" height="85vh">
                <v-row
                  class="fill-height d-flex align-center justify-center"
                  align="center"
                  justify="center"
                  tag="v-card-text"
                >
                  <v-col cols="6" class="pt-0 mt-0 d-flex align-end justify-center">
                    <v-img :src="`../assets/photo${project.image}.png`" max-height="70vh"></v-img>
                    <!-- src="../assets/pokemon.png" -->
                  </v-col>
                  <v-col cols="6">
                    <v-container
                      background-color="red"
                      class="px-12 d-flex flex-column "
                    >
                      <p class="display-2">{{ project.name }}</p>
                      <p class="title font-weight-thin mb-5">
                        {{ project.type }}
                      </p>
                      <div class="d-flex justify-space-around flex-wrap" width="40">
                        <div
                          v-for="lang in project.lang"
                          :key="lang"
                          class="d-flex my-10"
                        >
                          <v-icon :color="lang.color" x-large class="mr-5">
                            {{ lang.icon }}
                          </v-icon>
                          <p class="title font-weight-thin">{{ lang.name }}</p>
                        </div>
                      </div>

                      <p class="title font-weight-thin my-10">
                        {{ project.details }}
                      </p>

                      <!-- Link to a URL -->

                      <v-icon x-large>mdi-git</v-icon>
                      <p>GitHub</p>
                    </v-container>
                  </v-col>
                </v-row>
              </v-card>
            </v-window-item>
          </v-window>

          <v-card-actions class="justify-space-between">
            <v-btn text @click="prev">
              <v-icon>mdi-chevron-left</v-icon>
            </v-btn>
            <v-item-group v-model="onboarding" class="text-center" mandatory>
              <v-item
                v-for="n in length"
                :key="`btn-${n}`"
                v-slot:default="{ active, toggle }"
              >
                <v-btn :input-value="active" icon @click="toggle">
                  <v-icon>mdi-record</v-icon>
                </v-btn>
              </v-item>
            </v-item-group>
            <v-btn text @click="next">
              <v-icon>mdi-chevron-right</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  data: () => ({
    langs: [
      { title: "Vue.js", icon: "mdi-vuejs", color: "green" },
      { title: "HTML", icon: "mdi-language-html5", color: "orange" },
      { title: "CSS", icon: "mdi-language-css3", color: "blue" },
      { title: "JavaScript", icon: "mdi-language-javascript", color: "yellow" },
      { title: "SASS", icon: "mdi-sass", color: "pink" },
      { title: "LESS", icon: "mdi-code-tags", color: "green" },
      { title: "C#", icon: "mdi-language-csharp", color: "purple" },
      { title: "C++", icon: "mdi-language-cpp", color: "blue" }
    ],
    frameworks: [
      { title: "Vuetify", icon: "mdi-vuejs", color: "blue" },
      { title: "Bootstrap", icon: "mdi-bootstrap", color: "purple" },
      { title: "Flexbox", icon: "mdi-language-css3", color: "orange" },
      { title: "CSS Grid", icon: "mdi-language-css3", color: "blue" }
    ],
    softwares: [
      { title: "VS Code", icon: "mdi-visual-studio-code", color: "blue" },
      { title: "Adobe Illustrator", icon: "mdi-adobe", color: "red" },
      { title: "Adobe InDesign", icon: "mdi-adobe", color: "red" },
      { title: "Adobe XD", icon: "mdi-adobe", color: "red" },
      { title: "Google Sketchup", icon: "mdi-google", color: "green" },
      { title: "Xactimate", icon: "mdi-alpha-x-circle", color: "blue" },
      { title: "FileZilla", icon: "mdi-upload-multiple", color: "red" }
    ],
    additionals: [
      { title: "Netlify", icon: "mdi-server", color: "teal" },
      { title: "UX/UI Design", icon: "mdi-pencil-ruler", color: "orange" },
      { title: "WordPress", icon: "mdi-wordpress", color: "blue" },
      { title: "Bluehost", icon: "mdi-view-dashboard", color: "blue" },
      { title: "Git Certified", icon: "mdi-git", color: "pink" },
      { title: "A+ Training", icon: "mdi-desktop-tower", color: "white" },
      { title: "App Design", icon: "mdi-pencil-ruler", color: "orange" }
    ],
    experiences: [
      { title: "Node.js", icon: "mdi-nodejs", color: "green" },
      { title: "MongoDB", icon: "mdi-nodejs", color: "green" },
      { title: "Express", icon: "mdi-nodejs", color: "blue" },
      { title: "Mongoose", icon: "mdi-nodejs", color: "blue" },
      { title: "React", icon: "mdi-react", color: "blue" }
    ],
    length: 7,
    onboarding: 0,
    projects: [
      {
        name: "Keystroke App",
        type: "Senior Capstone Project",
        color: "purple",
        image: "../assets/starwars.png",
        lang: [
          { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
          { name: "Vuetify", icon: "mdi-vuejs", color: "blue" },
          { name: "Node.js", icon: "mdi-nodejs", color: "green" },
          { name: "MongoDB", icon: "mdi-nodejs", color: "green" },
          { name: "Express", icon: "mdi-nodejs", color: "blue" },
          { name: "Mongoose", icon: "mdi-nodejs", color: "blue" }
        ],
        details:
          "For my Senior Captsone project, my group and I were asked to make a web app. Our requirements were to:",
        list: [
          {item: 'Create testing platform'},
          {item: ''},
        ]
      },
      {
        name: "Weather App",
        type: "School Project",
        color: "purple",
        image: '1',
        lang: [
          { name: "React", icon: "mdi-react", color: "blue" },
          { name: "Material-UI", icon: "mdi-material-ui", color: "blue" }
        ],
        details:
          "This is a project we had to complete in under a week. I learned as much React as I could in that amount of time and made what you see here."
      },
      {
        name: "Car Garage",
        type: "School Project",
        color: "teal",
        image: "../assets/starwars.png",
        lang: [
          { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
          { name: "Vuetify", icon: "mdi-vuejs", color: "blue" }
        ],
        details:
          "This project was over one semester where we learned Vue.js. I learned how to do state management to allow the user to create a dream garage. I had a lot of fun with this project."
      },
      {
        name: "Star Wars API",
        type: "School Project",
        color: "indigo",
        image: "../assets/starwars.png",
        lang: [
          { name: "HTML", icon: "mdi-language-html5", color: "orange" },
          { name: "CSS", icon: "mdi-language-css3", color: "blue" },
          {
            name: "JavaScript",
            icon: "mdi-language-javascript",
            color: "yellow"
          }
        ],
        details:
          "For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout."
      },
      {
        name: "Pokemon API",
        type: "School Project",
        color: "indigo",
        image: "../assets/pokemon.png",
        lang: [
          { name: "HTML", icon: "mdi-language-html5", color: "orange" },
          { name: "CSS", icon: "mdi-language-css3", color: "blue" },
          {
            name: "JavaScript",
            icon: "mdi-language-javascript",
            color: "yellow"
          }
        ],
        details:
          "For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout."
      },
      {
        name: "Boka",
        type: "Client Project",
        color: "teal",
        image: "../assets/starwars.png",
        lang: [
          { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
          { name: "Vuetify", icon: "mdi-vuejs", color: "blue" },
          {
            name: "JavaScript",
            icon: "mdi-language-javascript",
            color: "yellow"
          }
        ],
        details:
          "For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout."
      }
    ]
  }),

  methods: {
    next() {
      this.onboarding =
        this.onboarding + 1 === this.length ? 0 : this.onboarding + 1;
    },
    prev() {
      this.onboarding =
        this.onboarding - 1 < 0 ? this.length - 1 : this.onboarding - 1;
    }
  }
};
</script>
