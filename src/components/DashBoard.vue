<!-- <template>
  <div>
    <v-container fluid>
      <v-card
        sm8
        md6
        lg3
        width="100%"
        class="blue darken-4 d-flex justify-center align-center"
        height="95vh"
      >
        <div>
          <v-img
            lazy-src="../assets//Yoganathan PP.png"
            src="../assets//Yoganathan PP.png"
            alt="profileimage"
            max-width="150px"
            height="170px"
            class="mx-auto photo"
            light
          />
          <v-spacer></v-spacer>
          <strong class="white--text text-h2 d-flex justify-center"
            >Yoganathan M</strong
          >
          <br />
          <p class="text-h4 d-flex justify-center">Software Developer</p>
          <br />
          <span
            ><v-icon medium>mdi-email</v-icon> yoganathanm11@gmail.com
            <v-icon medium>mdi-phone</v-icon> +91 9626210602
            <v-icon medium> mdi-map-marker-radius</v-icon> chennai, india</span
          >
        </div>
      </v-card>
    </v-container>
  </div>
</template>

<style>
.photo {
  border: 5px solid rgb(118, 25, 205);
  border-radius: 360%;
}
</style> -->

<template>
  <v-app>
    <v-container fluid class="fill-height pa-0 profile-bg">
      <v-row no-gutters class="fill-height" align="center" justify="center">
        <!-- ── DESKTOP (lg+): sidebar layout ── -->
        <v-col
          v-if="$vuetify.breakpoint.lgAndUp"
          cols="12"
          lg="3"
          class="fill-height"
        >
          <v-card
            flat
            tile
            class="sidebar-card fill-height d-flex flex-column align-center justify-center pa-8"
          >
            <div class="profile-avatar-wrap mb-6">
              <v-img
                lazy-src="../assets/Yoganathan PP.png"
                src="../assets/Yoganathan PP.png"
                alt="Yoganathan M profile photo"
                width="160"
                height="160"
                class="profile-avatar"
              />
              <div class="avatar-ring" />
            </div>

            <h1 class="profile-name text-center white--text mb-1">
              Yoganathan M
            </h1>
            <p class="profile-role text-center mb-6">Software Developer</p>

            <v-divider class="divider-glow mb-6" />

            <div class="contact-list">
              <div
                class="contact-item"
                v-for="item in contacts"
                :key="item.icon"
              >
                <v-icon small class="contact-icon mr-2">{{ item.icon }}</v-icon>
                <span class="contact-text">{{ item.text }}</span>
              </div>
            </div>

            <v-divider class="divider-glow mt-6 mb-6" />

            <!-- ── Resume Buttons ── -->
            <div class="resume-actions d-flex justify-center">
              <v-btn
                small
                class="resume-btn"
                @click="DownloadResume"
              >
                <v-icon small left>mdi-download</v-icon>
                Resume Download
              </v-btn>
            </div>
          </v-card>
        </v-col>

        <!-- ── TABLET (sm–md): centered card ── -->
        <v-col v-else-if="$vuetify.breakpoint.smAndUp" cols="12" sm="8" md="6">
          <v-card class="tablet-card mx-auto pa-8">
            <v-row no-gutters align="center" class="mb-6">
              <v-col cols="auto" class="mr-6">
                <div class="profile-avatar-wrap">
                  <v-img
                    lazy-src="../assets/Yoganathan PP.png"
                    src="../assets/Yoganathan PP.png"
                    alt="Yoganathan M profile photo"
                    width="110"
                    height="110"
                    class="profile-avatar"
                  />
                  <div class="avatar-ring" />
                </div>
              </v-col>
              <v-col>
                <h1 class="profile-name white--text mb-1">Yoganathan M</h1>
                <p class="profile-role mb-0">Software Developer</p>
              </v-col>
            </v-row>

            <v-divider class="divider-glow mb-5" />

            <div class="contact-list mb-5">
              <div
                class="contact-item"
                v-for="item in contacts"
                :key="item.icon"
              >
                <v-icon small class="contact-icon mr-2">{{ item.icon }}</v-icon>
                <span class="contact-text">{{ item.text }}</span>
              </div>
            </div>

            <!-- ── Resume Buttons ── -->
            <div class="resume-actions d-flex justify-center">
             
              <v-btn
                small
                class="resume-btn"
                @click="DownloadResume"
              >
                <v-icon small left>mdi-download</v-icon>
                Resume Download
              </v-btn>
            </div>
          </v-card>
        </v-col>

        <!-- ── MOBILE (xs): full-width stacked card ── -->
        <v-col v-else cols="12" class="px-4">
          <v-card class="mobile-card pa-6">
            <div class="d-flex flex-column align-center mb-5">
              <div class="profile-avatar-wrap mb-4">
                <v-img
                  lazy-src="../assets/Yoganathan PP.png"
                  src="../assets/Yoganathan PP.png"
                  alt="Yoganathan M profile photo"
                  width="100"
                  height="100"
                  class="profile-avatar"
                />
                <div class="avatar-ring" />
              </div>
              <h1 class="profile-name white--text text-center mb-1">
                Yoganathan M
              </h1>
              <p class="profile-role text-center mb-0">Software Developer</p>
            </div>

            <v-divider class="divider-glow mb-4" />

            <div class="contact-list mb-4">
              <div
                class="contact-item"
                v-for="item in contacts"
                :key="item.icon"
              >
                <v-icon small class="contact-icon mr-2">{{ item.icon }}</v-icon>
                <span class="contact-text">{{ item.text }}</span>
              </div>
            </div>

            <!-- ── Resume Buttons ── -->
            <div class="resume-actions d-flex justify-center">
             
              <v-btn
                small
                class="resume-btn"
                @click="DownloadResume"
              >
                <v-icon small left>mdi-download</v-icon>
               Resume Download
              </v-btn>
            </div>
            </v-card
          >
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: "ProfileCard",
  data: () => ({
    contacts: [
      { icon: "mdi-email", text: "yoganathanm11@gmail.com" },
      { icon: "mdi-phone", text: "+91 9626210602" },
      { icon: "mdi-map-marker-radius", text: "Chennai, India" },
      {
        icon: "mdi-linkedin",
        text: "https://linkedin.com/in/yoganathan-m-b99480393",
      },
    ],
  }),
  methods:{
    DownloadResume(){
      fetch('./Yoganathan_Dev.pdf')
      .then((res)=>res.blob())
      .then((blob) => {
        const url = URL.createObjectURL(blob);
        const a = document.createElement("a");
        a.href = url;
        a.download = "Yoganathan Dev.pdf";
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        URL.revokeObjectURL(url);
      })
      .catch(() => {
        window.open("/Yoganathan Dev.pdf", "_blank");
      });
    }
  }
};
</script>

<style scoped>
/* ── Background ── */
.profile-bg {
  min-height: 100vh;
  background: linear-gradient(135deg, #0d0d2b 0%, #1a1a4e 50%, #0d0d2b 100%);
}

/* ── Sidebar card (desktop) ── */
.sidebar-card {
  background: linear-gradient(180deg, #0c1a5e 0%, #071040 100%) !important;
  border-right: 1px solid rgba(130, 80, 255, 0.25);
}

/* ── Tablet card ── */
.tablet-card {
  background: linear-gradient(135deg, #0c1a5e 0%, #071040 100%) !important;
  border-radius: 20px !important;
  border: 1px solid rgba(130, 80, 255, 0.3);
  box-shadow: 0 8px 40px rgba(0, 0, 0, 0.5), 0 0 0 1px rgba(130, 80, 255, 0.1) !important;
}

/* ── Mobile card ── */
.mobile-card {
  background: linear-gradient(160deg, #0c1a5e 0%, #071040 100%) !important;
  border-radius: 16px !important;
  border: 1px solid rgba(130, 80, 255, 0.3);
  box-shadow: 0 4px 24px rgba(0, 0, 0, 0.5) !important;
}

/* ── Avatar ── */
.profile-avatar-wrap {
  position: relative;
  display: inline-block;
}

.profile-avatar {
  border-radius: 50% !important;
  border: 3px solid #7619cd;
  display: block;
}

.avatar-ring {
  position: absolute;
  inset: -6px;
  border-radius: 50%;
  border: 2px solid rgba(118, 25, 205, 0.4);
  animation: pulse-ring 2.5s ease-in-out infinite;
  pointer-events: none;
}

@keyframes pulse-ring {
  0%,
  100% {
    transform: scale(1);
    opacity: 0.5;
  }
  50% {
    transform: scale(1.08);
    opacity: 1;
  }
}

/* ── Typography ── */
.profile-name {
  font-size: clamp(1.2rem, 4vw, 1.8rem);
  font-weight: 700;
  letter-spacing: 0.5px;
  line-height: 1.2;
}

.profile-role {
  color: #a78bfa;
  font-size: clamp(0.85rem, 2.5vw, 1rem);
  font-weight: 500;
  letter-spacing: 1.5px;
  text-transform: uppercase;
}

/* ── Divider ── */
.divider-glow {
  border-color: rgba(118, 25, 205, 0.4) !important;
  box-shadow: 0 0 6px rgba(118, 25, 205, 0.3);
  width: 100%;
}

/* ── Contact list ── */
.contact-list {
  width: 100%;
}

.contact-item {
  display: flex;
  align-items: center;
  padding: 6px 0;
  border-radius: 8px;
  transition: background 0.2s;
}

.contact-item:hover {
  background: rgba(118, 25, 205, 0.12);
  padding-left: 6px;
}

.contact-icon {
  color: #a78bfa !important;
  flex-shrink: 0;
}

.contact-text {
  color: #cbd5e1;
  font-size: clamp(0.75rem, 2vw, 0.88rem);
  word-break: break-all;
}

/* ── Skill chips ── */
.skill-chip {
  background: rgba(118, 25, 205, 0.25) !important;
  color: #c4b5fd !important;
  border: 1px solid rgba(118, 25, 205, 0.5) !important;
  font-size: 0.72rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  transition: background 0.2s, transform 0.2s;
}

.skill-chip:hover {
  background: rgba(118, 25, 205, 0.45) !important;
  transform: translateY(-1px);
}

/* ── Resume buttons ── */
.resume-actions {
  width: 100%;
}

.resume-btn {
  background: rgba(118, 25, 205, 0.25) !important;
  color: #c4b5fd !important;
  border: 1px solid rgba(118, 25, 205, 0.5) !important;
  font-size: 0.72rem !important;
  font-weight: 600 !important;
  letter-spacing: 0.5px;
  text-transform: uppercase;
  transition: background 0.2s, transform 0.2s;
}

.resume-btn:hover {
  background: rgba(118, 25, 205, 0.5) !important;
  transform: translateY(-1px);
}
</style>