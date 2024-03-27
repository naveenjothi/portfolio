<template>
  <div
    data-aos="fade-up"
    data-aos-duration="3000"
    class="min-h-screen w-full px-4 md:px-10 flex flex-col md:flex-row items-center justify-center"
  >
    <div class="flex flex-col md:flex-row items-center justify-center w-full">
      <!-- Tabs -->
      <div class="w-1/2">
        <ul class="flex flex-wrap justify-center md:justify-start">
          <li
            v-for="tab in tabs"
            :key="tab.label"
            class="mx-4 my-2 cursor-pointer"
            :class="{
              'text-primary border-b-4 border-primary': activeTab === tab.label,
            }"
            @click="activeTab = tab.label"
          >
            {{ tab.label }}
          </li>
        </ul>
        <span v-if="tabData?.content" class="text-left">
          {{ tabData?.content }}
        </span>
      </div>

      <!-- Content -->
      <div class="md:flex-1 text-center md:text-left py-4 md:py-0">
        <!-- Content for Development Skills tab -->
        <div v-if="activeTab === tabs[0].label">
          <UiProgress :skills="developmentSkills" />
        </div>
        <div v-if="activeTab === tabs[1].label">
          <UiProgress :skills="developmentSkills" />
        </div>
        <div v-if="activeTab === tabs[2].label">
          <UiProgress :skills="developmentSkills" />
        </div>
        <!-- Add similar blocks for other tabs -->
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const developmentSkills = ref([
  { name: "JavaScript", level: 80 },
  { name: "React", level: 95 },
]);

const tabs = ref([
  {
    label: "Development Skills",
    content: "chjbnsaklmlscka",
  },
  {
    label: "Operational Skills",
    content: "",
  },
  {
    label: "Analytical Skills",
    content: "",
  },
]);

const activeTab = ref<string>(tabs.value[0].label);

const tabData = computed(() =>
  tabs.value.find((x) => x.label == activeTab.value)
);
</script>

<style scoped>
/* Add any additional styles or overrides here */
/* Ensure mobile responsiveness */
@media (max-width: 768px) {
  .flex-col.md\:flex-row {
    flex-direction: column;
  }
}
</style>
