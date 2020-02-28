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
              :key="lang.title"
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
              :key="framework.title"
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
              :key="software.title"
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
              :key="additional.title"
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
                :key="experience.title"
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
        <h2 class="display-1 text-center font-weight-thin">My Projects</h2>
        <v-card
          color="red lighten-4"
          height="100px"
          class="d-flex align-center justify-center black--text my-6 display-1"
          >This section is currently being developed</v-card
        >
        <!-- MY WORK -->
        <v-card flat tile class="mt-6">
          <v-window v-model="onboarding" vertical>
            <v-window-item v-for="project in projects" :key="project.name">
              <v-card :color="project.color" height="85vh">
                <v-row
                  class="fill-height d-flex align-center justify-center"
                  align="center"
                  justify="center"
                >
                  <v-col
                    cols="6"
                    class="pt-0 mt-0 d-flex align-end justify-center"
                  >
                    <v-img
                      :src="`../assets/photo${project.image}.png`"
                      max-height="70vh"
                    ></v-img>
                    <!-- src="../assets/pokemon.png" -->
                  </v-col>
                  <v-col cols="6">
                    <v-container
                      background-color="red"
                      class="py-0 d-flex flex-column justify-space-between"
                    >
                      <p class="display-2">{{ project.name }}</p>
                      <p class="title font-weight-thin mb-5">
                        {{ project.type }}
                      </p>
                      <div
                        class="d-flex justify-space-around flex-wrap"
                        width="40"
                      >
                        <div
                          v-for="lang in project.lang"
                          :key="lang.name"
                          class="d-flex"
                        >
                          <v-icon :color="lang.color" x-large class="mr-5">
                            {{ lang.icon }}
                          </v-icon>
                          <p class="title font-weight-thin">{{ lang.name }}</p>
                        </div>
                      </div>

                      <p class="title font-weight-thin text-left pt-3">
                        {{ project.details }}
                      </p>
                      <div>
                        <p class="title font-weight-regular">Project Requirements</p>
                        <v-list-item>
                          <v-list-item-content>
                            <v-list-item-title class="text-left pl-12" v-for="proj in project.list" :key="proj.item">✔ {{ proj.item }}</v-list-item-title>
                          </v-list-item-content>
                        </v-list-item>
                      </div>
                      <center>
                          <v-icon :to="project.url" x-large>mdi-git</v-icon>
                          <p>GitHub</p>
                      </center>                     
                                           
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
      { title: "React", icon: "mdi-react", color: "blue" },
      { title: "Next.js", icon: "mdi-react", color: "blue" }
    ],
    length: 7,
    onboarding: 0,
    projects: [
      {
        name: "Keystroke App",
        url: "#",
        type: "Senior Capstone Project",
        color: "purple",
        image: "../assets/starwars.png",
        lang: [
          { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
          { name: "Vuetify", icon: "mdi-vuejs", color: "blue" },
          { name: "Node.js", icon: "mdi-nodejs", color: "green" }
        ],
        details:
          "For my Senior Captsone project, my group and I were asked to make a web app. Our requirements were to:",
        list: [
          { item: "Create testing platform for staff and students" }, 
          { item: "Allow teachers to create their own quizzes" },
          { item: "Record students 'keystrokes' using JavaScript" },
          { item: "Record data in a database" },
          { item: "Allow teachers to create their own quizzes" },
          ]
      },
      {
        name: "Weather App",
        url: "",
        type: "School Project",
        color: "blue darken-4",
        image: "1",
        lang: [
          { name: "React", icon: "mdi-react", color: "blue" },
          { name: "Material-UI", icon: "mdi-material-ui", color: "blue" }
        ],
        details:
          "This is a project we had to complete in under a week. I learned as much React as I could in that amount of time and made what you see here.",
        list: [
          { item: "Display 1 week of weather" },
          { item: "Ability to switch between C° and F°" },
          { item: "Search weather by zipcode provided by user" },
          ]
      },
      {
        name: "Car Garage",
        url: "https://github.com/CobyYates/SuperCars",
        type: "School Project",
        color: "teal",
        image: "../assets/starwars.png",
        lang: [
          { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
          { name: "Vuetify", icon: "mdi-vuejs", color: "blue" }
        ],
        details:
          "This project was over one semester where we learned Vue.js. I learned how to do state management to allow the user to create a dream garage. I had a lot of fun with this project.",
        list: [
          { item: "Encapsulate code as VueJS single-file components" },
          { item: "Communicate between components using props & local store" },
          { item: "Create user form with validation and feedback" },
          { item: "Create a custom directive" },
          { item: "Use animations and transitions" },
          { item: "Connect to an API using Axios" },
          { item: "Manage your application's state using vuex" },
          ]
      },
      {
        name: "Star Wars API",
        url: "",
        type: "School Project",
        color: "grey darken-3",
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
          "For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout.",
        list: [
          { item: "" },
          ]
      },
      {
        name: "Pokemon API",
        url: "",
        type: "School Project",
        color: "red darken-2",
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
          "For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout.",
        list: [
          { item: "" },
          ]
      },
      {
        name: "Boka",
        url: "",
        type: "Client/Passion Project",
        color: "purple darken-2",
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
          "For this project, my brother wanted to make a CRM for photographers.",
        list: [
          { item: "Create a CRM for content creators" },
          { item: "Create dashboard for content creators" },
          ]
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
