<template>
  <div class="expecience-container">
    <v-container class="mx-auto">
      <div class="content-container py-16">
        <div class="exp-header my-16">
          <h3>Where I've Worked</h3>
        </div>
        <div class="exp-body d-flex">
          <div class="place-container pr-7">
            <ul class="place-list">
              <li class="place-item">
                <ButtonComponent class="text-start" :content="'3S Intersoft'" />
              </li>
              <li>
                <ButtonComponent
                  class="text-start pt-5"
                  :content="'Axon Active'"
                />
              </li>
            </ul>
          </div>
          <div class="work-description pl-7">
            <div class="work-header-desc">
              <p class="major text-start">
                Developer - <a href="">3S Intersoft</a>
              </p>
              <p class="time text-start">2022 - Present</p>
            </div>
            <div class="work-body-desc pt-5">
              <ul class="work-body-list">
                <li class="work-body-item">
                  <p class="work-body-text text-start">
                    Applied the KafkaJS module for inter-system data transfer,
                    along with related technologies and techniques such as
                    Postgresql and Docker
                  </p>
                </li>
                <li>
                  <p class="work-body-text text-start">
                    Contributed to the development of user interfaces for one
                    year using the Angular framework in conjunction with
                    Material, enhancing the user experience
                  </p>
                </li>
                <li>
                  <p class="work-body-text text-start">
                    Participated in the Scrum methodology, executed task
                    processes, and contributed to the completion of features
                    within each sprint of various projects
                  </p>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </v-container>
  </div>
</template>
<script lang="ts">
import ButtonComponent from "../button/button.vue";
export default {
  name: "ExperienceComponent",
  components: {
    ButtonComponent,
  },
};
</script>
<style scoped lang="scss">
@import url("../../../styles/scss/common/base.scss");
@import "../../../styles/settings.scss";

.expecience-container {
  position: relative;
  margin-top: 32px;
  height: 100%;
  text-align: center;

  .content-container {
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;

    .place-list {
      list-style: none;
    }

    .work-description {
      padding-top: 1px;

      .work-header-desc {
        .major {
          font-size: 20px;
        }
      }

      .work-body-desc {
        position: relative;
        ul {
          list-style: none;

          li > .work-body-text {
            &::before {
              content: "▹";
              font-size: 20px;
              position: absolute;
              left: -30px;
              color: $text-main-color;
            }
          }
        }
      }
    }
  }
  .exp-header {
    text-align: start;
    color: $text-main-color;
    font-size: 24px;
  }
}
</style>
