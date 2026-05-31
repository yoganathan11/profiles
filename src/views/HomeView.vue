<template>
  <div>
    <DashBoard />
    <AboutContent />
    <v-spacer></v-spacer>
    <SkillContent />
    <EducationContent />
    <ProjectContent />
    <ContactContent />
  </div>
</template>

<script>
import DashBoard from "../components/DashBoard";
import AboutContent from "../components/AboutContent.vue";
import SkillContent from "../components/SkillContent.vue";
import EducationContent from "@/components/EducationContent.vue";
import ContactContent from "@/components/ContactContent.vue";
import ProjectContent from "@/components/ProjectContent.vue";

export default {
  name: "HomePage",

  components: {
    DashBoard,
    AboutContent,
    SkillContent,
    EducationContent,
    ContactContent,
    ProjectContent,
  },
};
</script>
