<script setup>
  import { resumeData } from './resumeData';
  import Header from './Header.vue';

  function generate() {
    
  }
</script> 

<template>
  <Header
    :data="resumeData.header"
  ></Header>
</template>

<style>
html, body {
  margin: 0;
  padding: 0;
}

#app {
  padding: 0.75in;
  width: 8.5in;
  height: 11in;
}
/* Target the print media type */  
@media print {  
  /* Define print page settings */  
  @page {
    size: auto;  /* Use the printer's default paper size */  
    margin: 0mm; /* Remove all margins (no space for headers/footers) */
  }  
 
  /* Optional: Reset body margins to avoid extra space */  
  body {  
    margin: 0;  
    padding: 0;  
  }  
}  
</style>
