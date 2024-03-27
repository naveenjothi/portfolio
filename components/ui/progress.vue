<template>
  <div class="text-gray-900">
    <div
      v-for="(skill, idx) in skills"
      :key="skill.name"
      class="my-8 relative"
      :ref="`skillRef${idx}`"
    >
      <div class="flex justify-between mb-1">
        <span>{{ skill.name }}</span>
      </div>

      <div class="bg-gray-700 h-0.5 w-full rounded relative">
        <transition name="progress">
          <div
            class="h-0.5 rounded bg-[#629677] absolute top-0 left-0"
            :style="{ width: `${animatedLevel[skill.name]}%` }"
          ></div>
        </transition>
        <div
          class="tooltip-wrapper"
          :style="{ left: `calc(${animatedLevel[skill.name]}% - 10px)` }"
        >
          <div class="tooltip-tail"></div>
          <div
            class="tooltip-arrow bg-gray-900 text-white text-xs rounded py-1 px-2"
          >
            {{ animatedLevel[skill.name] }}%
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
interface ISkills {
  name: string;
  level: number;
}

const animatedLevel = ref<{ [key: string]: number }>({});
const scrolledPercentage = ref<number[]>([]);
const skillRefs = ref<HTMLElement[]>([]);

const props = defineProps({
  skills: {
    type: Array<ISkills>,
    required: true,
  },
});

const { skills } = toRefs(props);

onMounted(() => {
  animateSkills();
  observeSkills();
});

function animateSkills() {
  skills.value.forEach((skill) => {
    let currentLevel = 0;
    const interval = setInterval(() => {
      currentLevel++;
      animatedLevel.value[skill.name] = currentLevel;
      if (currentLevel >= skill.level) {
        clearInterval(interval);
      }
    }, 60); // adjust the animation speed as needed
  });
}

function observeSkills() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, index) => {
      if (entry.isIntersecting) {
        const scrolled = Math.min(entry.intersectionRatio * 100, 100);
        scrolledPercentage.value[index] = Math.round(scrolled);
      }
    });
  });

  skillRefs.value.forEach((ref) => {
    observer.observe(ref);
  });
}
</script>

<style scoped lang="scss">
.width-enter-active,
.width-leave-active {
  transition: width 0.5s ease-in-out;
}

.width-enter,
.width-leave-to {
  width: 0;
}

.tooltip-tail {
  width: 0;
  height: 0;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 4px solid #000;
  position: absolute;
  bottom: 100%;
  right: 50%;
  transform: translateX(50%);
}

.tooltip-wrapper {
  position: absolute;
  top: -1px;
}

.tooltip-arrow {
  position: absolute;
  bottom: calc(100% + 4px);
  right: 50%;
  transform: translateX(50%);
}
</style>
