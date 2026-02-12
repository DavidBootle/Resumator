<script setup>
    import { ref } from 'vue';

    defineProps(['data']);

    let isNameShown = ref(true);
    let isPhoneShown = ref(true);
    let isEmailShown = ref(true);
    let isWebsiteShown = ref(true);
    let isAddressShown = ref(true);
</script>

<template>
    <div class="header">
        <div v-if="isNameShown" @click="isNameShown = !isNameShown" class="name">{{ data.name }}</div>
        <div class="row">
            <div v-if="isEmailShown" @click="isEmailShown = !isEmailShown" class="row-content">{{ data.email }}</div>
            <div v-if="isPhoneShown" @click="isPhoneShown = !isPhoneShown" class="row-content">{{ data.phone }}</div>
            <div v-if="isWebsiteShown" @click="isWebsiteShown = !isWebsiteShown" class="row-content">{{ data.website }}</div>
        </div>
        <div v-if="isAddressShown" @click="isAddressShown = !isAddressShown" class="row-content">{{ data.address }}</div>
    </div>
</template>

<style scoped>

.header {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
}

.name {
    font-family: 'Oswald';
    font-size: 40px;
    font-weight: bold;
    font-variant: small-caps;
}

.row {
    display: flex;
    flex-direction: row;
    width: 100%;
    justify-content: center;
    align-items: center;
}

.row-content {
    font-size: 15px;
    font-family: 'Oswald';
}

.row > *:not(:last-child)::after {
  content: "|";
  margin: 10px;
}
</style>