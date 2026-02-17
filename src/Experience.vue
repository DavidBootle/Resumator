<script setup>
import { ref } from 'vue';

const props = defineProps(['data']);

let isShown = ref(true);
let description = ref(
    Array.isArray(props.data.description)
        ? [...props.data.description]
        : props.data.description
);

const removeDescriptionLineItem = (index) => {
    if (!Array.isArray(description.value)) return;

    description.value.splice(index, 1);

    if (!description.value.length) {
        description.value = null;
    }
};
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
        <div v-if="description" @click.stop class="experience-description">
            <div v-if="Array.isArray(description)">
                <div v-for="(item, index) in description" v-bind:key="`${item}-${index}`" @click.stop="removeDescriptionLineItem(index)">• {{ item }}</div>
            </div>
            <div v-else>{{ description }}</div>
        </div>
    </div>
</template>

<style scoped>
.experience-container {
    margin-top: 0.1in;
    padding-left: 0.25in;
    width: calc(100% - 0.25in);
    font-family: 'Oswald';
    font-size: 11pt;
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
    padding-left: 0.25in;
}
</style>
