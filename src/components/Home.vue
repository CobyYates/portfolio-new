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
                <p>{{ lang.title }}</p>
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
                <p>{{ framework.title }}</p>
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
                <p>{{ software.title }}</p>
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
                <p>{{ additional.title }}</p>
              </v-col>
            </div>
          </v-col>
        </v-row>
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
      { title: "VS Code", icon: "mdi-microsoft-visual-studio", color: "green" },
      { title: "Adobe Illustrator", icon: "mdi-adobe", color: "red" },
      { title: "Adobe InDesign", icon: "mdi-adobe", color: "red" },
      { title: "Adobe XD", icon: "mdi-adobe", color: "red" },
      { title: "Google Sketchup", icon: "mdi-google", color: "green" },
      { title: "Xactimate", icon: "mdi-alpha-x-circle", color: "blue" },
      { title: "FileZilla", icon: "mdi-", color: "purple" }
    ],
    additionals: [
      { title: "Netlify", icon: "mdi-", color: "green" },
      { title: "UX/UI Design", icon: "mdi-", color: "orange" },
      { title: "WordPress", icon: "mdi-wordpress", color: "blue" },
      { title: "Bluehost", icon: "mdi-", color: "yellow" },
      { title: "Git Certified", icon: "mdi-git", color: "pink" },
      { title: "A+ Training", icon: "mdi-", color: "green" },
      { title: "App Design", icon: "mdi-", color: "purple" }
    ],
    experiences: [
      { title: "Node.js", icon: "mdi-vuejs", color: "green" },
      { title: "MongoDB", icon: "mdi-language-html5", color: "orange" },
      { title: "Express", icon: "mdi-language-css3", color: "blue" },
      { title: "Mongoose", icon: "mdi-language-javascript", color: "yellow" },
      { title: "React", icon: "mdi-sass", color: "pink" }
    ]
  })
};
</script>
