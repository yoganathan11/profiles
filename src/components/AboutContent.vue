<!-- <template>
  <v-container>
    <strong class="text-h3 d-flex justify-center font-weight-medium"
      >About Me</strong
    >
    <v-card
      class="d-flex justify-center align-center mx-16"
      height="40vh"
      width="60rem"
      elevation="1"
    >
      <v-row class="d-flex justify-center">
        <v-col>
          <v-spacer></v-spacer>
          <p class="d-flex justify-center">
            Software Developer with hands-on experience in full-stack
            development, specializing in Golang backend <br />and Vue.js
            frontend. Experienced in building and integrating RESTful APIs,
            working with SQL databases, <br />and developing scalable and
            efficient applications. Passionate about writing clean code, solving
            problems, and <br />
            continuous learning. Seeking growth-oriented software development
            opportunities
          </p>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template> -->

<template>
  <v-container fluid class="about-section py-10 py-md-16 px-4 px-sm-8 px-md-16">
    <!-- Section Title -->
    <h2 class="section-title text-center mb-2">About Me</h2>
    <div class="title-underline mx-auto mb-8 mb-md-12" />

    <!-- Card -->
    <v-row justify="center">
      <v-col cols="12" sm="11" md="9" lg="7" xl="6">
        <v-card class="about-card pa-6 pa-sm-8 pa-md-10" elevation="0">
          <!-- Quote icon -->
          <v-icon class="quote-icon mb-4" large>mdi-format-quote-open</v-icon>

          <p class="about-text">
            Software Developer with hands-on experience in full-stack
            development, specializing in Golang backend and Vue.js frontend.
            Experienced in building and integrating RESTful APIs, working with
            SQL databases, and developing scalable and efficient applications.
            Passionate about writing clean code, solving problems, and
            continuous learning. Seeking growth-oriented software development
            opportunities.
          </p>

          <!-- Tech tags -->
          <div class="tag-row mt-6">
            <span v-for="tag in tags" :key="tag" class="tech-tag">{{
              tag
            }}</span>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "AboutMe",
  data: () => ({
    tags: ["Golang", "Vue.js", "REST APIs", "SQL", "Full-Stack"],
  }),
};
</script>

<style scoped>
/* ── Section wrapper ── */
.about-section {
  background: linear-gradient(160deg, #0d0d2b 0%, #1a1a4e 100%);
  min-height: 60vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
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

/* ── Card ── */
.about-card {
  background: rgba(255, 255, 255, 0.04) !important;
  border: 1px solid rgba(118, 25, 205, 0.3);
  border-radius: 18px !important;
  backdrop-filter: blur(12px);
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.4), 0 0 0 1px rgba(118, 25, 205, 0.08) !important;
  transition: box-shadow 0.3s ease;
}

.about-card:hover {
  box-shadow: 0 12px 50px rgba(118, 25, 205, 0.2),
    0 0 0 1px rgba(118, 25, 205, 0.2) !important;
}

/* ── Quote icon ── */
.quote-icon {
  color: rgba(118, 25, 205, 0.5) !important;
  font-size: 2.5rem !important;
  display: block;
}

/* ── Body text ── */
.about-text {
  color: #cbd5e1;
  font-size: clamp(0.9rem, 2.2vw, 1.05rem);
  line-height: 1.85;
  margin: 0;
}

/* ── Tech tags ── */
.tag-row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tech-tag {
  display: inline-block;
  padding: 4px 14px;
  border-radius: 20px;
  background: rgba(118, 25, 205, 0.2);
  border: 1px solid rgba(118, 25, 205, 0.45);
  color: #c4b5fd;
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 0.6px;
  text-transform: uppercase;
  transition: background 0.2s, transform 0.2s;
  cursor: default;
}

.tech-tag:hover {
  background: rgba(118, 25, 205, 0.4);
  transform: translateY(-2px);
}
</style>
