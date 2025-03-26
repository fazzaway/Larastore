<script setup>
import { Head, Link } from "@inertiajs/vue3";
import { defineProps, onMounted, ref } from "vue";

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
});
import AppLayout from "@/Layouts/AppLayout.vue";
import Banner from "@/Layouts/Banner.vue";
import PageSection from "@/Layouts/PageSection.vue";
import SectionBanner from "@/Layouts/SectionBanner.vue";

const services = ref([]);
const fetchHomeData = "/data/home-data.json";

onMounted(async ()=> {
    const response = await fetch(fetchHomeData);
    const data = await response.json();
    services.value = data.services;
})
</script>
<template>
    <AppLayout title="Total Trees">
        <Banner text="Managing your valuable tree assets, skillfully, cost effectively, promptly." img="/images/home-banner.webp"></Banner>
        <SectionBanner heading="Welcome">
            <template #heading>
                Total Tree Services
            </template>
            <template #paragraph>
                    <p>
                        18 years ago, Total Tree Services founder Jamie Nairn channelled his passion for managing trees and flora into a career as a qualified arborist. Benefit from his experience and that of his professional team when deciding on the best options for managing your tree assets, whether it’s tree lopping, pruning or removal.
                    </p>
                    <p>
                        Total Tree Services is committed to providing cost-effective and environmentally sound tree management services to clients in the Toowoomba region and across the Darling Downs, rural and regional Queensland, and the eastern states of Australia.
                    </p>
                    <p>
                        Providing professional and cost-effective tree management services are more than just having a chainsaw and ladder. Whether you are seeking a ‘one-off’ tree service, or ongoing tree management work, you can depend on Total Tree Services to deliver on your tree management or clearing requirements.
                    </p>
            </template>
            <div class="w-full max-w-[65rem] mx-auto grid grid-cols-5 gap-1 pt-4">
                <div class="flex flex-col gap-1" v-for="(service, index) in services" :key="index" >
                    <div class="w-full max-w-40 mx-auto">
                        <img :src="`${service.logo}`" :alt="`${service.title} logo`" />
                    </div>
                    <div class="text-center">
                        {{ service.title }}
                    </div>
                </div>
            </div>
        </SectionBanner>

        <PageSection>

        </PageSection>
    </AppLayout>
</template>

<style scoped></style>
