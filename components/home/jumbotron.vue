<template>
  <section id="hero" class="jumbotron">
    <div class="container">
      <h1 class="hero-title load-hidden">
        Hey, there !
        <br />
        I'm
        <span class="text-color-main">Naveen Jothi</span>
      </h1>

      <p class="hero-content">
        I'm a professional software engineer creating scalable architecture for
        modern websites
      </p>
    </div>
  </section>
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
