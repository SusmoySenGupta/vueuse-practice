<script setup>
import { useFullscreen } from '@vueuse/core';

const { isFullscreen, toggle } = useFullscreen();
</script>
<template>
    <button @click="toggle">
        <svg v-if="!isFullscreen" class="btn" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 8V4m0 0h4M4 4l5 5m11-1V4m0 0h-4m4 0l-5 5M4 16v4m0 0h4m-4 0l5-5m11 5l-5-5m5 5v-4m0 4h-4" />
        </svg>
        <svg v-else-if="isFullscreen" class="iconify iconify--uil btn" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" preserveAspectRatio="xMidYMid meet" viewBox="0 0 24 24">
            <path d="M16 9h5a1 1 0 0 0 0-2h-4V3a1 1 0 0 0-2 0v5a1 1 0 0 0 1 1zm-8 6H3a1 1 0 0 0 0 2h4v4a1 1 0 0 0 2 0v-5a1 1 0 0 0-1-1zM8 2a1 1 0 0 0-1 1v4H3a1 1 0 0 0 0 2h5a1 1 0 0 0 1-1V3a1 1 0 0 0-1-1zm13 13h-5a1 1 0 0 0-1 1v5a1 1 0 0 0 2 0v-4h4a1 1 0 0 0 0-2z" fill="currentColor" />
        </svg>
    </button>
</template>
<style lang="postcss" scoped>
.btn {
    @apply w-5 h-5 dark:text-slate-200 text-slate-500;
}
</style>