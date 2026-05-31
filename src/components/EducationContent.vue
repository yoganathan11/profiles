<!-- <template>
  <v-container fluid>
    <strong class="text-h3 d-flex justify-center font-weight-medium">
      Education</strong
    >
    <div class="d-flex justify-center mb-6">
      <v-card height="25vh" width="100vh" class="box pa-5" elevation="6">
        <v-row>
          <v-col cols="2">
            <v-icon large class="school Anime">mdi-school</v-icon>
          </v-col>
          <v-col cols="10">
            <v-chip medium class="info ml-3">Bachelor's degree</v-chip>
            <p>
              <v-icon>mdi-school</v-icon> B.E - Electronics And Communication
              Engineering
            </p>
            <p>
              <v-icon>mdi-map-marker</v-icon>M.Kumarasamy College of
              Engineering,Karur
            </p>
            <p><v-icon>mdi-calendar-month</v-icon> 2023</p>
          </v-col>
        </v-row>
      </v-card>
    </div>
    <div class="d-flex justify-center mb-6">
      <v-card height="25vh" width="100vh" class="box pa-5" elevation="6">
        <v-row>
          <v-col cols="2">
            <v-icon large class="school">mdi-school</v-icon>
          </v-col>
          <v-col cols="10">
            <v-chip medium class="info ml-3">Computer Science</v-chip>
            <p><v-icon>mdi-school</v-icon>Higher Secondary Education (HSC)</p>
            <p>
              <v-icon>mdi-map-marker</v-icon>Nehru Higher Secondary School,
              Puthanampatti
            </p>
            <p><v-icon>mdi-calendar-month</v-icon> 2019</p>
          </v-col>
        </v-row>
      </v-card>
    </div>
    <div class="d-flex justify-center">
      <v-card height="25vh" width="100vh" class="box pa-5" elevation="6">
        <v-row>
          <v-col cols="2">
            <v-icon large class="school">mdi-school</v-icon>
          </v-col>
          <v-col cols="10">
            <v-chip medium class="info ml-3">Secondary Education</v-chip>
            <v-spacer></v-spacer>
            <p><v-icon>mdi-school</v-icon>Secondary School (SSLC)</p>

            <p>
              <v-icon>mdi-map-marker</v-icon>Nehru Higher Secondary School,
              Puthanampatti
            </p>
            <p><v-icon>mdi-calendar-month</v-icon> 2017</p>
          </v-col>
        </v-row>
      </v-card>
    </div>
  </v-container>
</template>

<style scoped>
.box {
  border-left: 4px solid rgb(255, 2, 2);
}
.school {
  border: 9px solid rgb(55, 55, 232);
  border-radius: 360%;
}

@keyframes Anime {
  0% {
    background-color: aqua;
  }
  50% {
    background-color: blueviolet;
  }
  100% {
    background-color: yellow;
  }
}
</style> -->

<template>
  <v-container
    fluid
    class="education-section py-10 py-md-16 px-4 px-sm-8 px-md-16"
  >
    <!-- Section Title -->
    <h2 class="section-title text-center mb-2">Education</h2>
    <div class="title-underline mx-auto mb-8 mb-md-12" />

    <!-- Timeline -->
    <v-row justify="center">
      <v-col cols="12" sm="10" md="8" lg="7" xl="6">
        <div class="timeline">
          <div v-for="(edu, i) in education" :key="i" class="timeline-item">
            <!-- Connector dot -->
            <div class="timeline-dot">
              <v-icon small color="#a78bfa">mdi-school</v-icon>
            </div>

            <!-- Card -->
            <v-card
              class="edu-card pa-5 pa-sm-6 ml-6 ml-sm-8 mb-6"
              elevation="0"
            >
              <!-- Badge + Year -->
              <div class="card-top mb-3">
                <span class="badge">{{ edu.badge }}</span>
                <span class="year ml-auto">
                  <v-icon x-small class="mr-1" color="#a78bfa"
                    >mdi-calendar-month</v-icon
                  >
                  {{ edu.year }}
                </span>
              </div>

              <!-- Degree -->
              <div class="info-row mb-2">
                <v-icon small class="info-icon mr-2"
                  >mdi-book-open-variant</v-icon
                >
                <span class="info-text degree">{{ edu.degree }}</span>
              </div>

              <!-- Institution -->
              <div class="info-row">
                <v-icon small class="info-icon mr-2">mdi-map-marker</v-icon>
                <span class="info-text">{{ edu.institution }}</span>
              </div>
            </v-card>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "EducationContent",
  data: () => ({
    education: [
      {
        badge: "Bachelor's Degree",
        year: "2023",
        degree: "B.E — Electronics & Communication Engineering",
        institution: "M. Kumarasamy College of Engineering, Karur",
      },
      {
        badge: "Computer Science",
        year: "2019",
        degree: "Higher Secondary Education (HSC)",
        institution: "Nehru Higher Secondary School, Puthanampatti",
      },
      {
        badge: "Secondary Education",
        year: "2017",
        degree: "Secondary School (SSLC)",
        institution: "Nehru Higher Secondary School, Puthanampatti",
      },
    ],
  }),
};
</script>

<style scoped>
/* ── Section ── */
.education-section {
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

/* ── Timeline wrapper ── */
.timeline {
  position: relative;
  padding-left: 8px;
}

/* Vertical line */
.timeline::before {
  content: "";
  position: absolute;
  left: 15px;
  top: 0;
  bottom: 0;
  width: 2px;
  background: linear-gradient(180deg, #7619cd 0%, rgba(118, 25, 205, 0.1) 100%);
  border-radius: 2px;
}

/* ── Timeline item ── */
.timeline-item {
  position: relative;
  display: flex;
  align-items: flex-start;
}

/* ── Dot ── */
.timeline-dot {
  position: relative;
  z-index: 1;
  flex-shrink: 0;
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background: rgba(118, 25, 205, 0.25);
  border: 2px solid rgba(118, 25, 205, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 18px;
  animation: pulse-dot 2.8s ease-in-out infinite;
}

@keyframes pulse-dot {
  0%,
  100% {
    box-shadow: 0 0 0 0 rgba(118, 25, 205, 0.4);
  }
  50% {
    box-shadow: 0 0 0 7px rgba(118, 25, 205, 0);
  }
}

/* ── Edu card ── */
.edu-card {
  flex: 1;
  background: rgba(255, 255, 255, 0.04) !important;
  border: 1px solid rgba(118, 25, 205, 0.3);
  border-left: 3px solid #7619cd !important;
  border-radius: 14px !important;
  backdrop-filter: blur(12px);
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.35) !important;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.edu-card:hover {
  transform: translateX(4px);
  box-shadow: 0 8px 36px rgba(118, 25, 205, 0.18),
    0 0 0 1px rgba(118, 25, 205, 0.2) !important;
}

/* ── Card top row ── */
.card-top {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
}

.badge {
  display: inline-block;
  padding: 3px 12px;
  border-radius: 20px;
  background: rgba(118, 25, 205, 0.22);
  border: 1px solid rgba(118, 25, 205, 0.45);
  color: #c4b5fd;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.6px;
  text-transform: uppercase;
}

.year {
  display: flex;
  align-items: center;
  color: #94a3b8;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 0.4px;
}

/* ── Info rows ── */
.info-row {
  display: flex;
  align-items: flex-start;
}

.info-icon {
  color: #7619cd !important;
  margin-top: 2px;
  flex-shrink: 0;
}

.info-text {
  color: #cbd5e1;
  font-size: clamp(0.82rem, 2vw, 0.95rem);
  line-height: 1.5;
}

.degree {
  color: #e2e8f0;
  font-weight: 600;
}
</style>
