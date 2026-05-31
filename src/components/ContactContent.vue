<template>
  <v-container
    fluid
    class="contact_content py-10 py-md-16 px-4 px-sm-8 px-md-16"
  >
    <div class="text-center mb-10">
      <h2 class="text-center mb-2 section-title">let's work Together</h2>
      <div class="title-underline mx-auto"></div>

      <p class="section-subtitle mx-auto my-4">
        I'm always open to discussing new projects, creative ideas, or
        opportunities to be part of your vision.
      </p>
    </div>
    <v-row justify="center" align="stretch" class="gap-row">
      <v-col
        cols="12"
        sm="6"
        md="4"
        v-for="social in socials"
        :key="social.name"
      >
        <div class="d-flex align-center justify-center flex-column gap-4">
          <v-card
            elevation="3"
            align="center"
            class="con1 pa-4"
            style="width: 80%"
            @click="SendMessage(social.title)"
          >
            <a :href="url" target="_blank">
              <v-icon class="white--text" color="info">{{
                social.icon
              }}</v-icon>
              <v-card-text class="white--text">{{ social.title }} </v-card-text>
              <v-card-text class="white--text">{{ social.name }}</v-card-text>
            </a>
          </v-card>
          <v-spacer></v-spacer>
        </div>
      </v-col>
      <v-spacer></v-spacer><v-spacer></v-spacer>
    </v-row>
    <v-divider class="mt-10 grey lighten-4"></v-divider>
    <div align="center" class="pa-3">
      <span>© 2026 Yoganathan M. All rights reserved.</span>
    </div>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      socials: [
        {
          icon: "mdi-email",
          title: "Email",
          name: "yoganathanm11@gmail.com",
        },
        {
          icon: "mdi-phone",
          title: "Phone",
          name: "+919626210602",
        },
        {
          icon: "mdi-map-marker",
          title: "Location",
          name: "Chennai",
        },
      ],
      url: "",
    };
  },
  methods: {
    SendMessage(title) {
      if (title === "Email") {
        this.url = "https://www.gmail.com";
      } else if (title === "Phone") {
        this.url = "https://www.whatsapp.com";
      } else if (title === "Location") {
        this.url = "https://www.google.com/maps";
      }
      // console.log("title name :", title);
    },
  },
};
</script>

<style scoped>
.tab1 {
  background-color: #121238;
}
.contact_content {
  color: white;
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
.con1 {
  background-color: #121238;
  transform: translateX(4px);
  box-shadow: 0 8px 36px rgba(118, 25, 205, 0.18),
    0 0 0 1px rgba(118, 25, 205, 0.2) !important;
  border: 1px solid rgba(118, 25, 205, 0.3);
  border-left: 3px solid #7619cd;
  border-right: 3px solid #7619cd;
  border-radius: 14px !important;
}
.con1:hover {
  flex: 1;
  background-color: #121238;
  background: rgba(255, 255, 255, 0.04) !important;
  box-shadow: 0px 4px 25px rgb(0, 0, 0, 0.35) !important;
  border: 1px solid rgba(118, 25, 205, 0.3);
  border-left: 3px solid #7619cd;
  border-right: 3px solid #7619cd;
  border-radius: 14px !important;
  backdrop-filter: blur(12px);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  transform: scale(1.04);
}
.section-eyebrow {
  font-size: 0.75rem;
  font-weight: 600;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: #a78bfa;
}
.section-title {
  color: #ffffff;
  font-size: clamp(1.8rem, 5vw, 2.6rem);
  font-weight: 800;
  letter-spacing: 1px;
}
a {
  text-decoration: none;
}
</style>
