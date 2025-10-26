<template lang="pug">
    div(class="bg-red-200 h-screen  py-[40px]" ref="section1") 
        UContainer
            p {{ title }}
    div(class="bg-green-200 h-screen  py-[40px]" ref="section2") 
        UContainer 
            p {{ title }}
    div(class="bg-blue-200 h-screen  py-[40px]" ref="section3") 
        UContainer 
            p {{ title }}
</template>

<script setup lang="ts">
const route = useRoute();
const title = route.params.projectTitle as string;
const section = route.params.section as string;

const section2 = ref<HTMLElement | null>(null);
const section3 = ref<HTMLElement | null>(null);
const isVisible = ref(false);
const activeSection = ref<string | null>(null);

useIntersectionObserver(section2, (entry) => {
  console.log(entry);
});

// useIntersectionObserver(section3, ([{ isIntersecting }]) => {
//   if (activeSection.value === "section3") return;
//   activeSection.value = isIntersecting ? "section3" : activeSection.value;
//   if (isIntersecting) {
//     navigateTo(`/projects/${title}/third-section`);
//   }
// });
</script>

<style scoped></style>
