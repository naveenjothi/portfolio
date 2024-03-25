<template>
  <div class="container mx-auto px-4 bg-[#E6EFEA]">
    <header class="flex justify-between items-center py-6">
      <div>
        <a href="/">
          <img
            src="../../assets/resources/nj-logo-bg-removed.png"
            alt="Logo image"
            class="mx-auto rounded-full w-24 h-24 object-cover"
          />
        </a>
      </div>
      <!-- Navigation -->
      <nav>
        <ul class="flex space-x-4">
          <li>
            <a
              href="/contact"
              class="text-white bg-[#629677] hover:bg-purple-700 px-4 py-2 rounded-full"
              >Say Hello</a
            >
          </li>
        </ul>
      </nav>
    </header>
    <main class="text-center my-16">
      <!-- Hero Section -->
      <h1 class="text-5xl font-bold text-gray-900">
        Software Engineer & Team Contributor
      </h1>
      <p class="text-xl text-gray-700 mt-4">
        Crafting the Backbone of Modern Applications – A Journey with Naveen
        Jothi
      </p>
      <!-- Hero Image -->
      <div class="mt-8">
        <img
          src="../../assets/resources/nj-avatar.svg"
          alt="Your image"
          class="mx-auto rounded-full w-48 h-48 object-cover"
        />
      </div>
    </main>
  </div>
</template>

<style scoped lang="scss">
@import "../../assets/scss/_mixins.scss";
section {
  padding: 5rem 0rem;

  @include respond(phone) {
    border: none;
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
</style>
