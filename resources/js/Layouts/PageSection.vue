<script setup>
import { defineProps } from 'vue';

defineProps({
    heading: String,
});

</script>

<template>
    <section class="py-20">
        <div class="max-w-7xl mx-auto sm:px-6 lg:px-10">
            <div class="overflow-hidden">
                <slot></slot>
            </div>
        </div>

    </section>
</template>
