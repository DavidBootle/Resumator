<script setup>
import { ref } from 'vue';

const props = defineProps({
  data: {
    type: Array,
    required: true
  }
});
let skills = ref([...props.data]);

function removeItem(value) {
    skills.value = skills.value.filter(item => item !== value);
}

</script>

<template>
    <div class="skills-container">
        <div
            v-bind:key="skill"
            v-for="skill in skills"
            @click="removeItem(skill)"
            class="skill-item rotating"
        >
            • {{ skill }}
        </div>
    </div>
</template>

<style scoped>

.skills-container {
    margin-left: 0.25in;
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    margin-top: 0.1in;
}

.skill-item {
    font-family: 'Oswald';
    font-weight: 300;
    font-size: 11pt;
}

</style>