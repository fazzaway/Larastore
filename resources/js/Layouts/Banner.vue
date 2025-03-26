<script setup>
import { defineProps } from "vue";
defineProps({
    text: String,
    img: String,
    alt: String,
});
</script>

<template>
    <section
        class="bg-secondary overflow-hidden shadow-xl sm:rounded-lg bg-center bg-cover bg-no-repeat"
        :style="{ backgroundImage: 'url(' + img + ')' }"
    >
        <div class="max-w-7xl mx-auto sm:px-6 lg:px-10">
            <div class="h-[38.5rem] max-w-xl flex justify-start items-center">
                <div class="text-3xl text-white text-filter leading-normal">
                    <div>
                        {{ text }}
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style>
.text-filter {
    text-shadow: 0 0 4px rgba(0, 0, 0, 0.5);
}
</style>
