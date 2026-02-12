<script setup>
    import { ref } from 'vue';
    defineProps(['data']);

    let isShown = ref(true);
</script>

<template>
    <div v-if="isShown" @click="isShown = false;" class="education-container">
        <div class="left col">
            <div><span class="bold-text">{{ data.name }}</span> (GPA: {{ data.gpa }})</div>
            <i class="normal-text">{{ data.degree }}</i>
        </div>
        <div class="right col">
            <div class="normal-text">{{ data.location }}</div>
            <div class="normal-text">{{ data.timeRange }}</div>
            
        </div>
    </div>
</template>

<style scoped>

.education-container {
    margin-top: 8px;
    display: flex;
    flex-direction: row;
    justify-content: start;
    padding-left: 18px;
    width: calc(100%-18px);
    font-family: 'Oswald';
    font-size: 16px;
    font-weight: 300;
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