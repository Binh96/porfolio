<template>
  <div class="project-container">
    <div class="project-content-container py-16 my-16">
      <div class="project-header">
        <h3>What I've Build</h3>
      </div>
      <div class="project-body pt-16">
        <Carousel
          :itemsToShow="1"
          :itemsToScroll="1"
          :wrapAround="true"
          :autoplay="3000"
          :pauseAutoplayOnHover="true"
          :snapAlign="'center'"
          :mouseDrag="true"
          :touchDrag="true"
        >
          <Slide
            v-for="(item, index) in items"
            :key="index"
            :class="{ active: index === currentIndex }"
          >
            <img :src="item.image" alt="" />
          </Slide>
        </Carousel>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide } from "vue3-carousel";
import imgOne from "@/assets/img/temp1.jpg";
import imgTwo from "@/assets/img/temp2.jpg";
import imgThree from "@/assets/img/temp3.jpg";
import { ref } from "vue";

export default {
  name: "ProjectComponent",
  components: {
    Carousel,
    Slide,
  },
  data: () => {
    const currentIndex = ref(0);
    return {
      currentIndex,
      items: [
        {
          id: 1,
          title: "Slide 1",
          image: imgOne,
        },
        {
          id: 2,
          title: "Slide 2",
          image: imgTwo,
        },
        {
          id: 3,
          title: "Slide 3",
          image: imgThree,
        },
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
@import url("../../../styles/scss/common/base.scss");
@import "../../../styles/settings.scss";

.project-container {
  position: relative;
  margin-top: 32px;
  height: 100%;

  .project-content-container {
    max-width: 1000px;
    margin-left: auto;
    margin-right: auto;

    .project-header {
      color: $text-main-color;
      font-size: 24px;
    }

    .project-body {
      img {
        width: 100%;
        height: 420px;
      }

      .carousel .slide {
        opacity: 0.5; /* Đặt độ mờ cho tất cả các slide */
        transition: opacity 0.3s ease; /* Hiệu ứng chuyển tiếp */
      }

      .carousel .slide.active {
        opacity: 1; /* Đặt độ mờ cho slide chính */
      }
    }
  }
}
</style>
