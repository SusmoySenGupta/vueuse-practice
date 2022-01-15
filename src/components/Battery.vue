<script setup>
import { useBattery } from '@vueuse/core';
import { computed, ref } from 'vue';

const { charging, level } = useBattery();
const battery = ref(computed(() => Math.round(level.value * 100))); 
</script>
<template>
    <div class="flex items-center justify-center space-x-1">
        <span class="text-xs text-slate-700 dark:text-slate-200">{{ battery }}%</span>
        <!-- battery-charging -->
        <svg v-if="charging" class="iconify iconify--iconoir icn animate-pulse" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <g stroke-width="1.5" fill="none">
                <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
                <path d="M10.167 9L8.5 12h4l-1.667 3" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
            </g>
        </svg>
        <!-- battery-empty -->
        <svg v-else-if="battery <= 10" class="iconify iconify--iconoir icn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <g stroke-width="1.5" fill="none">
                <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
            </g>
        </svg>
        <!-- battery-25 -->
        <svg v-else-if="battery <= 25" class="iconify iconify--iconoir icn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <g stroke-width="1.5" fill="none">
                <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
                <path d="M4 14.4V9.6a.6.6 0 0 1 .6-.6h1.8a.6.6 0 0 1 .6.6v4.8a.6.6 0 0 1-.6.6H4.6a.6.6 0 0 1-.6-.6z" stroke="currentColor" />
            </g>
        </svg>
        <!-- battery-50 -->
        <span v-else-if="battery <= 50" class="text-red-500">
            <svg class="iconify iconify--iconoir icn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
                <g stroke-width="1.5" fill="none">
                    <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                    <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
                    <path d="M4 14.4V9.6a.6.6 0 0 1 .6-.6h4.8a.6.6 0 0 1 .6.6v4.8a.6.6 0 0 1-.6.6H4.6a.6.6 0 0 1-.6-.6z" stroke="currentColor" />
                </g>
            </svg>
        </span>
        <!-- battery-75 -->
        <svg v-else-if="battery <= 75" class="iconify iconify--iconoir icn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <g stroke-width="1.5" fill="none">
                <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
                <path d="M4 14.4V9.6a.6.6 0 0 1 .6-.6h8.8a.6.6 0 0 1 .6.6v4.8a.6.6 0 0 1-.6.6H4.6a.6.6 0 0 1-.6-.6z" stroke="currentColor" />
            </g>
        </svg>
        <!-- battery-full -->
        <svg v-else class="iconify iconify--iconoir icn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <g stroke-width="1.5" fill="none">
                <path d="M23 10v4" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M1 16V8a2 2 0 0 1 2-2h15a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2z" stroke="currentColor" />
                <path d="M4 14.4V9.6a.6.6 0 0 1 .6-.6h11.8a.6.6 0 0 1 .6.6v4.8a.6.6 0 0 1-.6.6H4.6a.6.6 0 0 1-.6-.6z" stroke="currentColor" />
            </g>
        </svg>
    </div>
</template>
<style lang="postcss" scoped>
.icn {
    @apply w-6 h-6 text-slate-700 dark:text-slate-200;
}
</style>