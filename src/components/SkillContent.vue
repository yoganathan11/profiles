<!-- <template>
  <v-container>
    <strong class="text-h3 font-weight-medium d-flex justify-center pa-3 mb-3"
      >Technical Skills</strong
    >

    <v-row>
      <v-col cols="4">
        <v-card
          height="130px"
          width="300px"
          class="cursor-hover pa-3"
          elevation="2"
        >
          <v-subheader class="d-flex justify-start font-weight-bold"
            >Frondend</v-subheader
          >

          <v-chip small class="ind-hover black--text blue lighten-5"
            >HTML</v-chip
          >

          <v-chip small class="ind-hover black--text blue lighten-5"
            >CSS</v-chip
          >

          <v-chip small class="ind-hover black--text blue lighten-5"
            >JavaScript</v-chip
          >
        </v-card>
      </v-col>
      <v-col cols="4">
        <v-card
          height="130px"
          width="300px"
          class="cursor-hover pa-3"
          elevation="2"
        >
          <v-icon large color="white" class="database">mdi-database</v-icon>
          <v-subheader class="d-flex justify-start font-weight-bold">
            Backend</v-subheader
          >

          <v-chip small class="ind-hover black--text blue lighten-5">
            GoLang</v-chip
          >
          <v-chip small class="ind-hover black--text blue lighten-5">
            Python</v-chip
          >
        </v-card>
      </v-col>
      <v-col cols="4">
        <v-card
          height="130px"
          width="300px"
          class="cursor-hover pa-3"
          elevation="2"
        >
          <v-subheader class="d-flex justify-start font-weight-bold"
            >Database</v-subheader
          >
          <v-chip small class="ind-hover black--text blue lighten-5">
            Postgres</v-chip
          >
          <v-chip small class="ind-hover black--text blue lighten-5">
            MySql</v-chip
          >
        </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col></v-col>
      <v-col cols="6">
        <v-card
          height="130px"
          width="300px"
          class="cursor-hover pa-3"
          elevation="2"
        >
          <v-subheader class="d-flex justify-start font-weight-bold"
            >Tools & Platforms</v-subheader
          >
          <v-chip small class="ind-hover black--text blue lighten-5"
            >Git & Github</v-chip
          >
          <v-chip small class="ind-hover black--text blue lighten-5"
            >VS Code</v-chip
          >
          <v-chip small class="ind-hover black--text blue lighten-5"
            >Postman</v-chip
          >
        </v-card>
      </v-col>
      <v-col cols="5">
        <v-card
          height="130px"
          width="300px"
          class="cursor-hover pa-3"
          elevation="2"
        >
          <v-subheader class="d-flex justify-start font-weight-bold"
            >Language</v-subheader
          ><v-chip small class="ind-hover black--text blue lighten-5"
            >Tamil</v-chip
          ><v-chip small class="ind-hover black--text blue lighten-5"
            >English</v-chip
          >
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
.cursor-hover {
  cursor: pointer;
  transition: 0.3s;
}
.cursor-hover:hover {
  transform: scale(1.05);
}
.ind-hover {
  cursor: pointer;
  transition: 0.3s;
}
.ind-hover:hover {
  background-color: rgba(41, 102, 255, 0.796) !important;
  color: white !important;
}
.database {
  border: 2px solid rgb(36, 101, 242);
  border-radius: 15%;
  background-color: rgb(8, 56, 161);
}
</style> -->

<template>
  <v-container
    fluid
    class="skills-section py-10 py-md-16 px-4 px-sm-8 px-md-16"
  >
    <!-- Section Title -->
    <h2 class="section-title text-center mb-2">Technical Skills</h2>
    <div class="title-underline mx-auto mb-8 mb-md-12" />

    <v-row justify="center">
      <v-col
        v-for="category in skillCategories"
        :key="category.title"
        cols="12"
        sm="6"
        lg="4"
        class="d-flex"
      >
        <v-card
          class="skill-card pa-5 flex-grow-1"
          align="center"
          elevation="0"
        >
          <!-- Icon + Title row -->
          <div class="card-header mb-4">
            <div class="icon-wrap mr-3">
              <v-icon :color="category.color">{{ category.icon }}</v-icon>
            </div>
            <span class="card-title">{{ category.title }}</span>
          </div>

          <!-- Chips -->
          <div class="chip-row">
            <span
              v-for="skill in category.skills"
              :key="skill"
              class="skill-chip"
              >{{ skill }}</span
            >
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "TechnicalSkills",
  data: () => ({
    skillCategories: [
      {
        title: "Frontend",
        icon: "mdi-monitor-dashboard",
        color: "#a78bfa",
        skills: ["HTML", "CSS", "JavaScript", "Vue.js", "Vuetify"],
      },
      {
        title: "Backend",
        icon: "mdi-server",
        color: "#a78bfa",
        skills: ["GoLang", "REST APIs", "WebSocket"],
      },
      {
        title: "Database",
        icon: "mdi-database",
        color: "#a78bfa",
        skills: ["PostgreSQL", "MySQL"],
      },
      {
        title: "Tools & Platforms",
        icon: "mdi-wrench",
        color: "#a78bfa",
        skills: ["Git & GitHub", "VS Code", "Postman", "Docker", "Kubernetes"],
      },
      {
        title: "Languages",
        icon: "mdi-translate",
        color: "#a78bfa",
        skills: ["Tamil", "English"],
      },
    ],
  }),
};
</script>

<style scoped>
/* ── Section wrapper ── */
.skills-section {
  background: linear-gradient(160deg, #0d0d2b 0%, #1a1a4e 100%);
  min-height: 60vh;
}

/* ── Title ── */
.section-title {
  color: #ffffff;
  font-size: clamp(1.6rem, 5vw, 2.4rem);
  font-weight: 700;
  letter-spacing: 1px;
}

.title-underline {
  width: 56px;
  height: 3px;
  background: linear-gradient(90deg, #7619cd, #a78bfa);
  border-radius: 2px;
}

/* ── Skill card ── */
.skill-card {
  background: rgba(255, 255, 255, 0.04) !important;
  border: 1px solid rgba(118, 25, 205, 0.3);
  border-radius: 16px !important;
  backdrop-filter: blur(12px);
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.35) !important;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  cursor: default;
}

.skill-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(118, 25, 205, 0.2),
    0 0 0 1px rgba(118, 25, 205, 0.25) !important;
}

/* ── Card header ── */
.card-header {
  display: flex;
  align-items: center;
}

.icon-wrap {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 36px;
  height: 36px;
  border-radius: 8px;
  background: rgba(118, 25, 205, 0.2);
  border: 1px solid rgba(118, 25, 205, 0.4);
  flex-shrink: 0;
}

.card-title {
  color: #e2e8f0;
  font-size: clamp(0.9rem, 2vw, 1rem);
  font-weight: 700;
  letter-spacing: 0.8px;
  text-transform: uppercase;
}

/* ── Chip row ── */
.chip-row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.skill-chip {
  display: inline-block;
  padding: 4px 14px;
  border-radius: 20px;
  background: rgba(118, 25, 205, 0.15);
  border: 1px solid rgba(118, 25, 205, 0.4);
  color: #c4b5fd;
  font-size: 0.78rem;
  font-weight: 600;
  letter-spacing: 0.4px;
  cursor: pointer;
  transition: background 0.2s, transform 0.2s, color 0.2s;
}

.skill-chip:hover {
  background: rgba(118, 25, 205, 0.45);
  color: #fff;
  transform: translateY(-2px);
}
</style>
