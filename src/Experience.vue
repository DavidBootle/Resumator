<script setup>
import { ref } from 'vue';

defineProps(['data']);

let isShown = ref(true);
let isDescriptionShown = ref(true);
</script>

<template>
    <div v-if="isShown" @click="isShown = false" class="experience-container">
        <div class="experience-header">
            <div class="col left">
                <div class="bold">{{ data.position }}</div>
                <div>{{ data.name }}</div>
            </div>
            <div class="col right">
                <div>{{ data.timeRange }}</div>
                <div>{{ data.location }}</div>
            </div>
        </div>
        <div v-if="isDescriptionShown && data.description" @click.stop="isDescriptionShown = false" class="experience-description">
            <i>{{ data.description }}</i>
        </div>
    </div>
</template>

<style scoped>
.experience-container {
    margin-top: 8px;
    padding-left: 18px;
    width: calc(100%-18px);
    font-family: 'Oswald';
    font-size: 16px;
    font-weight: 300;
}

.experience-header {
    display: flex;
    flex-direction: row;
    justify-content: start;
    width: 100%;
}

.col {
    display: flex;
    flex-direction: column;
    width: 50%;
}

.col.left {
    text-align: left;
}
.col.right {
    text-align: right;
}

.bold {
    font-weight: normal;
}

.experience-description {
    text-align: justify;
}
</style>