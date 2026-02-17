<script setup>
    import { ref } from 'vue';

    defineProps(['name']);

    let isShown = ref(true);
</script>

<template>
    <div v-if="isShown" @click="isShown=false;" class="section-header">{{ name }}</div>
</template>

<style scoped>
.section-header {
  font-family: 'Oswald';
  font-size: 14pt;
  width: 100%;
  border-bottom: 1px solid black;
  margin-top: 0.1in;
  font-variant: small-caps;
  font-weight: 600;
}
</style>