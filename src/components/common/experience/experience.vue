<template>
  <div class="expecience-container">
    <v-container class="mx-auto">
      <div class="content-container py-16">
        <div class="exp-header my-16">
          <h3>Where I've Worked</h3>
        </div>
        <div class="exp-body"></div>
      </div>
    </v-container>
  </div>
</template>
<script lang="ts">
export default {
  name: "ExperienceComponent",
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
  }
  .exp-header {
    text-align: start;
    color: $text-main-color;
    font-size: 24px;
  }
}
</style>
