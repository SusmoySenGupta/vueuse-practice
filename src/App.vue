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
                <!-- Github Logo -->
                <a href="https://github.com/SusmoySenGupta/vueuse-practice" target="_blank" class="text-slate-500 dark:text-slate-200">
                    <svg class="iconify iconify--icon-park-outline w-5 h-5" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 48 48">
                        <g fill="currentColor" fill-rule="evenodd" clip-rule="evenodd">
                            <path d="M24 4C12.954 4 4 12.954 4 24s8.954 20 20 20s20-8.954 20-20S35.046 4 24 4zM0 24C0 10.745 10.745 0 24 0s24 10.745 24 24s-10.745 24-24 24S0 37.255 0 24z" />
                            <path d="M19.183 45.471c-.193-.25-.193-2.474 0-6.673c-2.072.072-3.38-.072-3.927-.431c-.82-.54-1.64-2.2-2.367-3.371c-.728-1.171-2.343-1.356-2.995-1.618c-.652-.262-.816-1.328 1.797-.522c2.613.807 2.74 3.005 3.565 3.518c.824.514 2.795.29 3.689-.122c.893-.412.827-1.944.986-2.551c.202-.567-.508-.693-.524-.697c-.872 0-5.453-.997-6.712-5.433c-1.258-4.437.363-7.337 1.228-8.584c.576-.83.525-2.602-.153-5.313c2.463-.315 4.364.46 5.703 2.326c.002.01 1.755-1.043 4.527-1.043c2.772 0 3.755.858 4.514 1.043c.759.185 1.366-3.266 6.053-2.326c-.979 1.923-1.798 4.326-1.173 5.313c.626.988 3.08 4.128 1.572 8.584c-1.005 2.97-2.98 4.781-5.928 5.433c-.338.107-.507.281-.507.521c0 .36.457.4 1.115 2.087c.439 1.124.47 4.336.095 9.635c-.95.242-1.69.404-2.22.488c-.937.147-1.954.23-2.954.261c-1 .032-1.348.029-2.73-.1a19.798 19.798 0 0 1-2.654-.425z" />
                        </g>
                    </svg>
                </a>
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