<script setup>
    import { ref } from 'vue';
    defineProps(['data']);

    let isShown = ref(true);
    let isDescriptionShown = ref(true);
</script>

<template>
    <div v-if="isShown" @click="isShown = false;" class="education-container">
        <div class="education-header-row">
            <div class="left col">
                <div><span class="bold-text">{{ data.name }}</span> (GPA: {{ data.gpa }})</div>
                <i class="normal-text">{{ data.degree }}</i>
            </div>
            <div class="right col">
                <div class="normal-text">{{ data.location }}</div>
                <div class="normal-text">{{ data.timeRange }}</div>
            </div>
        </div>
        <div v-if="isDescriptionShown && data.description" @click.stop="isDescriptionShown = false;" class="education-description">
            {{ data.description }}
        </div>
    </div>
</template>

<style scoped>

.education-container {
    margin-top: 8px;
    padding-left: 18px;
    width: calc(100% - 18px);
    font-family: 'Oswald';
    font-size: 16px;
    font-weight: 300;
}

.education-header-row {
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

.bold-text {
    font-weight: normal;
}

</style>