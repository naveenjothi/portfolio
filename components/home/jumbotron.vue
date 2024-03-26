<template>
  <div class="container mx-auto px-4 min-h-screen bg-[#E6EFEA] animate-fadeIn">
    <header class="flex justify-between items-center py-6">
      <div class="animate-dropIn">
        <a href="/">
          <img
            src="../../assets/resources/nj-logo-bg-removed.png"
            alt="Logo image"
            class="rounded-full w-24 h-24 object-cover"
          />
        </a>
      </div>
      <!-- Navigation -->
      <nav>
        <ul class="flex space-x-4">
          <li class="animate-fadeIn delay-1000">
            <a
              href="/contact"
              class="text-white bg-[#629677] hover:bg-purple-700 transition-colors duration-300 px-3 py-2 rounded-full text-sm sm:text-base sm:px-4 sm:py-2 hover:scale-110"
              >Say Hello</a
            >
          </li>
        </ul>
      </nav>
    </header>
    <main class="text-center my-8 sm:my-16">
      <!-- Hero Section -->
      <h1
        class="text-3xl sm:text-5xl font-bold text-gray-900 animate-fadeIn delay-500"
      >
        Software Engineer & Team Contributor
      </h1>
      <p class="text-lg sm:text-xl text-gray-700 mt-4 animate-fadeIn delay-750">
        Crafting the Backbone of Modern Applications – A Journey with Naveen
        Jothi
      </p>
      <!-- Hero Image -->
      <div class="mt-4 sm:mt-8 animate-fadeIn delay-1000">
        <img
          src="../../assets/resources/nj-avatar.svg"
          alt="Your image"
          class="mx-auto rounded-full w-32 h-32 sm:w-48 sm:h-48 object-cover"
        />
      </div>
    </main>
  </div>
</template>

<style scoped lang="scss">
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes dropIn {
  0% {
    opacity: 0;
    transform: translateY(-50px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fadeIn {
  animation: fadeIn 1s ease-out forwards;
}

.animate-dropIn {
  animation: dropIn 0.5s ease-out forwards;
}

.delay-500 {
  animation-delay: 0.5s;
}

.delay-750 {
  animation-delay: 0.75s;
}

.delay-1000 {
  animation-delay: 1s;
}

/* Add hover effect for button */
a:hover {
  transform: scale(1.05);
  transition: transform 0.3s ease;
}
</style>
