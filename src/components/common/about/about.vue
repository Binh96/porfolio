import { ref } from 'vue'; import { ref } from 'vue';
<template>
  <div class="about-container">
    <v-container>
      <v-row class="d-flex justify-center align-center">
        <div class="content-container">
          <div class="about-header">
            <h1>Hi! I'm Binh</h1>
            <p>{{ contentAboutMe }}</p>
          </div>
          <div class="avatar-container">
            <img
              src="../../../assets\img\151980501_1640161342857644_5243743910150441001_n.jpg"
              alt=""
              class="circle circle-large"
            />
          </div>
        </div>
      </v-row>
    </v-container>
  </div>
</template>
<script lang="ts">
import { ref } from "vue";
import data from "../../../assets/data/user.json";

export default {
  name: "AboutComponent",
  components: {},
  data() {
    const contentAboutMe = ref<string>((() => data["about-me"])());

    return {
      contentAboutMe,
    };
  },
};
</script>
<style scoped lang="scss">
@import url("../../../styles/scss/common/base.scss");
@import "../../../styles/settings.scss";

.about-container {
  position: relative;
  margin-top: 30px;
  height: 100%;

  .about-header {
    position: absolute;
    top: 30%;
    left: 35%;
    transform: translate(-30%, -50%);
    color: $text-main-color;
    width: 450px;
  }

  .avatar-container {
    position: absolute;
    top: 36%;
    left: 50%;
  }
}
</style>
