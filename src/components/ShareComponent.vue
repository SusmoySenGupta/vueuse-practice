<script setup>
import { useShare } from '@vueuse/core';
import { ref } from 'vue';

const shareOptions = ref({
    title: 'Susmoy | VueUse Practice',
    text: 'VueUse Practice!',
    url: 'https://susmoysengupta.github.io/vueuse-practice/',
    hashtags: 'vueuse',
    via: 'vueuse',
    related: 'vueuse',
    image: 'https://d33wubrfki0l68.cloudfront.net/2f6479d73bc25170dc532dd42e059166573bf478/61057/favicon.svg',
});
const { share, isSupported } = useShare(shareOptions);
</script>
<template>
    <button v-if="isSupported" @click="share" class="flex items-center justify-center px-3 py-1 space-x-1 tracking-wide bg-teal-600 rounded text-slate-200">
        <svg class="w-6 h-6 iconify iconify--bx" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <path d="M3 12c0 1.654 1.346 3 3 3c.794 0 1.512-.315 2.049-.82l5.991 3.424c-.018.13-.04.26-.04.396c0 1.654 1.346 3 3 3s3-1.346 3-3s-1.346-3-3-3c-.794 0-1.512.315-2.049.82L8.96 12.397c.018-.131.04-.261.04-.397s-.022-.266-.04-.397l5.991-3.423c.537.505 1.255.82 2.049.82c1.654 0 3-1.346 3-3s-1.346-3-3-3s-3 1.346-3 3c0 .136.022.266.04.397L8.049 9.82A2.982 2.982 0 0 0 6 9c-1.654 0-3 1.346-3 3z" fill="currentColor" />
        </svg>
        Share
    </button>
</template>