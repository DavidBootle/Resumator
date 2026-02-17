<script setup>
    import { ref } from 'vue';
    import { Fa6Linkedin, Fa6Globe, Fa6Phone } from 'vue-icons-plus/fa6';
    import { FaHome } from 'vue-icons-plus/fa';
    import { FiMail } from 'vue-icons-plus/fi';

    defineProps(['data']);

    let isNameShown = ref(true);
    let isPhoneShown = ref(true);
    let isEmailShown = ref(true);
    let isWebsiteShown = ref(true);
    let isAddressShown = ref(true);
    let isLinkedinShown = ref(true);
</script>

<template>
    <div class="header">
        <div v-if="isNameShown" @click="isNameShown = !isNameShown" class="name">{{ data.name }}</div>
        <div class="row">
            <div v-if="isEmailShown" @click="isEmailShown = !isEmailShown" class="row-content"><FiMail size="15"/>&nbsp;{{ data.email }}</div>
            <div v-if="isPhoneShown" @click="isPhoneShown = !isPhoneShown" class="row-content"><Fa6Phone size="15"/>&nbsp;{{ data.phone }}</div>
            <div v-if="isWebsiteShown" @click="isWebsiteShown = !isWebsiteShown" class="row-content"><Fa6Globe size="15"/>&nbsp;<a :href="'https://' + data.website">{{ data.website }}</a></div>
        </div>
        <div class="row">
             <div v-if="isLinkedinShown" @click="isLinkedinShown = false" class="row-content"><Fa6Linkedin size="15"/>&nbsp;<a class="aligned" :href="'https://linkedin.com/in/' + data.linkedin">{{ data.linkedin }}</a></div>
            <div v-if="isAddressShown" @click="isAddressShown = !isAddressShown" class="row-content"><FaHome size="15"/>&nbsp;{{ data.address }}</div>
        </div>
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
    font-size: 28pt;
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
    font-size: 11pt;
    font-family: 'Oswald';
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

.aligned {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
}

.row > *:not(:last-child)::after {
  content: "|";
  margin-left: 0.1in;
  margin-right: 0.1in;
}
</style>