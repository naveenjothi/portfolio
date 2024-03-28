<template>
  <div
    data-aos="fade-up"
    data-aos-duration="3000"
    class="min-h-screen w-full px-4 md:px-10 flex flex-col md:flex-row items-center justify-center flex-wrap"
  >
    <div class="flex-auto w-full pt-12 ps-12">
      <ul class="flex flex-wrap space-x-4 border-b-2 border-slate-200">
        <li
          v-for="tab in tabs"
          :key="tab.label"
          class="cursor-pointer text-base px-4 py-3 relative z-0"
          @click="activeTab = tab.label"
        >
          <span
            :class="{
              'text-primary': activeTab === tab.label,
            }"
          >
            {{ tab.label }}
          </span>
          <div
            :class="{
              'bg-primary h-0.5 w-2/3 absolute bottom-0 z-[-1]':
                activeTab === tab.label,
            }"
          ></div>
        </li>
      </ul>
    </div>

    <div
      class="flex flex-col md:flex-row items-center justify-between w-full gap-10"
    >
      <div
        class="w-full md:w-2/5 p-6 flex-auto border border-slate-300 rounded-md min-h-[calc(100vh-160px)]"
      >
        <div
          v-if="tabData?.content"
          v-html="tabData.content"
          class="text-left"
        />
      </div>

      <div
        class="w-full md:w-2/5 text-center md:text-left p-6 flex-initial min-h-96"
      >
        <div
          v-if="activeTab === tabs[0].label"
          data-aos="fade-in"
          data-aos-duration="2000"
        >
          <UiProgress :skills="developmentSkills" />
        </div>
        <div
          v-if="activeTab === tabs[1].label"
          data-aos="fade-in"
          data-aos-duration="2000"
        >
          <UiProgress :skills="developmentSkills" />
        </div>
        <div
          v-if="activeTab === tabs[2].label"
          data-aos="fade-in"
          data-aos-duration="2000"
        >
          <UiProgress :skills="developmentSkills" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const developmentSkills = ref([
  { name: "JavaScript", level: 80 },
  { name: "React", level: 95 },
]);

const tabs = ref([
  {
    label: "Development Skills",
    content: `<p>
            <strong>Bringing Ideas to Life and Making Them Shine:</strong> At the heart of what I do lies a deep passion for development — a journey that goes beyond mere creation to also include the art of optimization. With a robust skill set in programming languages such as Python and JavaScript, I excel in crafting elegant solutions to complex problems and transforming them into user-friendly digital products. But the magic doesn't stop at launch; my expertise in site optimization ensures that these products are not only functional but also fast, responsive, and SEO-friendly. Whether it’s enhancing loading times, improving user experience, or ensuring websites rank well on search engines, my goal is to optimize every aspect of the digital products I develop. This commitment to excellence in both creation and refinement is what drives me forward, making each project not just a task, but a masterpiece of technology.
        </p>`,
  },
  {
    label: "Operational Skills",
    content: `<p>
            <strong>The Backbone of Success:</strong> Operations are where my analytical and pragmatic skills shine. My experience ranges from managing cloud infrastructures on platforms like AWS and Azure to ensuring continuous integration and deployment (CI/CD) processes run smoothly. I thrive on optimizing workflows, implementing best practices in software development lifecycle management, and guaranteeing high availability and performance of services. My operational expertise means I'm always prepared to keep the digital gears turning efficiently, ensuring that both team productivity and software reliability are always at their peak.
        </p>`,
  },
  {
    label: "Analytical Skills",
    content: `<p>
            <strong>Solving Puzzles with Data:</strong> Where there's data, there's insight waiting to be discovered. My analytical prowess is defined by my ability to dissect complex datasets, draw meaningful conclusions, and turn those insights into actionable strategies. With tools such as SQL for database management, Python for data analysis, and experience with machine learning models, I can not only predict trends but also prescribe solutions that drive success. My approach is always data-driven, ensuring decisions are not just gut feelings but well-informed strategies designed to achieve specific objectives.
        </p>`,
  },
]);

const activeTab = ref<string>(tabs.value[0].label);

const tabData = computed(() =>
  tabs.value.find((x) => x.label == activeTab.value)
);
</script>

<style scoped lang="scss">
/* Ensure mobile responsiveness */
@media (max-width: 768px) {
  .flex-col.md\:flex-row {
    flex-direction: column;
  }
}
</style>
