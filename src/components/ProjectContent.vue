<template>
  <v-container
    fluid
    class="education-section py-10 py-md-16 px-4 px-sm-8 px-md-16"
  >
    <!-- Section Title -->
    <h2 class="section-title text-center mb-2">Project</h2>
    <div class="title-underline mx-auto mb-8 mb-md-12" />

    <!-- Timeline -->
    <v-row justify="center">
      <v-col cols="12" sm="10" md="8" lg="7" xl="6">
        <div class="timeline">
          <div v-for="(proj, i) in project" :key="i" class="timeline-item">
            <!-- Connector dot -->
            <div class="timeline-dot">
              <v-icon small color="#a78bfa">mdi-briefcase</v-icon>
            </div>

            <!-- Card -->
            <v-card
              class="edu-card pa-5 pa-sm-6 ml-6 ml-sm-8 mb-6"
              elevation="0"
            >
              <!-- Badge + Year -->
              <div class="card-top mb-3">
                <span class="badge">{{ proj.title }}</span>
              </div>

              <div class="info-row mb-2">
                <v-icon small class="mr-1" color="#a78bfa"
                  >mdi-code-braces-box</v-icon
                >
                <span class="year ml-1">
                  {{ proj.Technology }}
                </span>
              </div>

              <!-- Description -->
              <div class="info-row">
                <v-icon small class="info-icon mr-2"
                  >mdi-book-open-variant</v-icon
                >
                <span class="info-text degree">{{ proj.Description }}</span>
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
  name: "ProjectContent",
  data: () => ({
    project: [
      {
        title: "External Api Response Tracker",
        Technology: "Vue.js 2, Golang, Rest API’s, PostgreSQL",
        Description:
          "Developed a Go (Golang)-based API monitoring system to track third-party API availability, success and failure rates, and response latency. Built REST API logging services in Go to capture request and response details, HTTP status codes, latency metrics, and error information in PostgreSQL. Implemented configurable retry mechanisms and structured error handling for third-party API failures to improve service reliability and stability. Developed a Vue.js 2 dashboard for real-time API health monitoring, filtering, status tracking, failure analysis, and latency trend visualization.",
      },
      {
        title: "Client Fund Tracker",
        Technology: "Vue.js 2, Golang, Rest API's, MySQL, PostgreSQL",
        Description:
          "Developed Go-based backend services and APIs to monitor client fund allocation and deallocation transactions across integrated systems. Implemented real-time fund movement monitoring and validation to improve transaction accuracy, traceability, and operational visibility. Developed automated validation logic to identify fund mismatches, including cases where funds were deallocated without a corresponding allocation to the target client. Implemented automated email alerts for critical transaction mismatches, enabling faster issue identification, investigation, and manual intervention.",
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
  color: #feffff;
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
  color: #9098a1;
  font-size: clamp(0.82rem, 2vw, 0.95rem);
  line-height: 1.5;
}

.degree {
  color: #b6bfca;
  font-weight: 600;
}
</style>
