<script setup>
  import { resumeData } from './resumeData';
  import Header from './Header.vue';
  import Education from './Education.vue';
  import SectionHeader from './SectionHeader.vue';
  import Experience from './Experience.vue';
  import Skills from './Skills.vue';

</script> 

<template>
  <Header
    :data="resumeData.header"
  />
  <SectionHeader name="Education"/>
  <Education
    v-for="education in resumeData.education"
    v-bind:key="education.name"
    :data="education"
  />
  <SectionHeader name="Experience"/>
  <Experience
    v-for="experience in resumeData.experience"
    v-bind:key="experience.name"
    :data="experience"
  />
  <SectionHeader name="Skills"/>
  <Skills
    :data="resumeData.skills"
  />
</template>

<style>

@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&family=Oswald:wght@200..700&family=Roboto+Slab:wght@100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');

html, body {
  margin: 0;
  padding: 0;
}

#app {
  padding: 0.75in;
  width: 8.5in;
  height: 11in;
  border: 1px solid black;
  overflow: scroll;
}

a {
  color: black;
  text-decoration: none;
  pointer-events: none;
}

/* Target the print media type */  
@media print {  
  /* Define print page settings */  
  @page {
    size: auto;  /* Use the printer's default paper size */  
    margin: 0mm; /* Remove all margins (no space for headers/footers) */
  }  

  #app {
    border: none;
    overflow: hidden;
  }
 
  /* Optional: Reset body margins to avoid extra space */  
  body {  
    margin: 0;  
    padding: 0;  
  }  

  a {
    text-decoration: underline;
    pointer-events: all;
  }
}  
</style>
