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
        <h2 class="display-1 mt-5">Coby Yates</h2>
        <v-row class="mt-12 ml-12">
          <v-col class="text-center">
            <h2 class="text-left">Languages</h2>
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
            <h2 class="text-left">Frameworks</h2>
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
            <h2 class="text-left">Software</h2>
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
            <h2 class="text-left">Additional</h2>
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
        <v-row>
          <v-col>
            <h2 class="mb-5">Experience with</h2>
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
    <v-row>
      <v-col class="text-center">
        <h2 class="display-1 text-center">My Work</h2>
          <!-- MY WORK -->
        <v-card flat tile class="mt-6">
          <v-window v-model="onboarding" vertical>
            <v-window-item v-for="project in projects" :key="project">
              <v-card color="grey" height="200">
                <v-row
                  class="fill-height"
                  align="center"
                  justify="center"
                  tag="v-card-text">
                    <v-col>
                      
                    </v-col>
                    <v-col>
                      <p>Name: {{ project.name }}</p>
                      <div class="d-flex justify-space-around" width="40">
                        <div v-for="lang in project.lang" :key="lang" class="d-flex align-baseline">
                          <v-icon :color="lang.color">{{ lang.icon }}</v-icon>
                          <p>{{ lang.name }}</p>
                        </div>
                      </div>
                      
                      <p>Project Type: {{ project.type }}</p>
                      <p>{{ project.details }}</p>
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
    length: 4,
    onboarding: 0,
    projects: [
      {name: 'Weather App',
      type: 'School Project',
      lang: [
        { name: 'React', icon: "mdi-react", color: "blue" },
        { name: 'Material-UI', icon: "mdi-material-ui", color: "blue" },
      ],
      details: 'This is a project we had to complete in under a week. I learned as much React as I could in that amount of time and made what you see here.'},
      {name: 'Car Garage',
      type: 'School Project',
      lang: [
        { name: 'Vue.js', icon: "mdi-vuejs", color: "green" },
        { name: 'Vuetify', icon: "mdi-vuejs", color: "blue" },
      ],
      details: 'This project was over one semester where we learned Vue.js. I learned how to do state management to allow the user to create a dream garage. I had a lot of fun with this project.'},
      {name: 'Star Wars API',
      type: 'School Project',
      lang: [
        { name: 'HTML', icon: "mdi-language-html5", color: "orange" },
        { name: "CSS", icon: "mdi-language-css3", color: "blue" },
        { name: "JavaScript", icon: "mdi-language-javascript", color: "yellow" },
      ],
      details: 'For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout.'},
      {name: 'Pokemon API',
      type: 'School Project',
      lang: [
        { name: 'HTML', icon: "mdi-language-html5", color: "orange" },
        { name: "CSS", icon: "mdi-language-css3", color: "blue" },
        { name: "JavaScript", icon: "mdi-language-javascript", color: "yellow" },
      ],
      details: 'For this project, I learned JavaScript for the first time. The project was to fetch data from an API and display it in a card layout.'}
    ]
  }),

    methods: {
      next () {
        this.onboarding = this.onboarding + 1 === this.length
          ? 0
          : this.onboarding + 1
      },
      prev () {
        this.onboarding = this.onboarding - 1 < 0
          ? this.length - 1
          : this.onboarding - 1
      },
    },
};
</script>
