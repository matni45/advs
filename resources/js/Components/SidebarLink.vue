<script setup>
import { computed } from 'vue';
import { Link } from '@inertiajs/inertia-vue3';

const props = defineProps(['href', 'active']);
const classes = computed(() => props.active
    ? 'px-4 py-2 flex items-center gap-4 hover:bg-white hover:text-slate-700 text-blue'
    : 'px-4 py-2 flex items-center gap-4 hover:bg-white hover:text-slate-700 text-blue'
);
</script>

<template>
    <Link :href="href" class="px-4 py-2 flex items-center gap-4 hover:bg-white hover:text-slate-700 text-blue">
        <slot />
    </Link>
</template>