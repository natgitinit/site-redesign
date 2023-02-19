<template>
  <div id="my-carousel" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-indicators">
      <button
        type="button"
        data-bs-target="#my-carousel"
        data-bs-slide-to="0"
        class="active"
      ></button>
      <button
        type="button"
        data-bs-target="#my-carousel"
        data-bs-slide-to="1"
      ></button>
      <button
        type="button"
        data-bs-target="#my-carousel"
        data-bs-slide-to="2"
      ></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
    </div>
    <button
      class="carousel-control-prev"
      type="button"
      data-bs-target="#my-carousel"
      data-bs-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button
      class="carousel-control-next"
      type="button"
      data-bs-target="#my-carousel"
      data-bs-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue";
import { Carousel } from "bootstrap";

export default class MyCarousel extends Vue {
  private carouselInstance!: Carousel;

  mounted() {
    // Initialize the carousel instance
    const carouselElement = document.getElementById("my-carousel");
    if (carouselElement) {
      this.carouselInstance = new Carousel(carouselElement);
    }
  }

  beforeUnmount() {
    // Dispose the carousel instance
    this.carouselInstance.dispose();
  }
}
</script>
