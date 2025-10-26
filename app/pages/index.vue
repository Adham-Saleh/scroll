<template lang="pug">
    UContainer(class="py-[40px]")
        h1.text-lg.font-bold.mb-3 Explore our projects!
        .grid.gap-3(class="lg:grid-cols-4")
            UCard(variant="subtle" v-for="project, idx in projects" :key="project?.id")
                h2.text-h4 {{ `#${idx + 1} ${project?.title}`}}
                UButton(variant="outline" class="mt-4 cursor-pointer" @click="navigateTo(`/projects/${project?.title}/first-section`)") Explore

</template>

<script setup lang="ts">
const projects = [
  { id: 1, title: "Baiitna" },
  { id: 2, title: "Tatmeen" },
  { id: 3, title: "Leiaqa" },
  { id: 4, title: "Catrek" },
];
</script>

<style scoped></style>
