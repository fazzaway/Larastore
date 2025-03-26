<script setup>
import { defineProps } from "vue";
defineProps({
    heading: String,
});
import PageSection from "./PageSection.vue";
</script>

<template>
    <PageSection>
        <h1 class="text-secondary text-center leading-tight">
            {{ heading }}
            <span class="block text-[3.375rem] text-primary font-medium">
                <slot name="heading"></slot>
            </span>
        </h1>
        <div class="max-w-32 my-3 bg-primary mx-auto h-[3px]"></div>
        <div class="text-center max-w-5xl mx-auto">
            <div class="flex flex-col justify-center items-center gap-4">
                <slot name="paragraph"></slot>
            </div>
        </div>
        <slot></slot>
    </PageSection>
</template>
