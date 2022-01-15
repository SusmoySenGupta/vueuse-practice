<script setup>
import { useTitle } from '@vueuse/core';
import Battery from './components/Battery.vue';
import FullScreen from './components/FullScreen.vue';
import ImageComponent from './components/ImageComponent.vue';
import OnlineChecker from './components/OnlineChecker.vue';
import ShareComponent from './components/ShareComponent.vue';
import ThemeTogglerButton from './components/ThemeTogglerButton.vue';

const title = useTitle('VueUse Practice | Susmoy Sen Gupta');
</script>

<template>
    <div class="relative w-full min-h-screen dark:bg-slate-900">
        <div class="fixed flex items-center justify-between w-full p-6 space-x-2">
            <div class="flex items-center justify-center space-x-2">
                <!-- Online Checker -->
                <online-checker></online-checker>
                <!-- Version -->
                <p class="left-0 text-xs font-semibold text-slate-800 dark:text-slate-200">V0.0.1</p>
            </div>
            <div class="flex items-center justify-center space-x-4">
                <!-- Theme Toggler -->
                <theme-toggler-button></theme-toggler-button>
                <!-- Full Screen -->
                <full-screen></full-screen>
            </div>
        </div>
        <div class="flex items-center justify-center w-full h-screen">
            <div class="flex flex-col items-center justify-center space-y-4">
                <h1 class="text-3xl font-bold text-slate-700 dark:text-slate-200">VueUse Practice!</h1>
                <share-component></share-component>
                <battery></battery>
            </div>
        </div>
        <image-component></image-component>
    </div>
</template>