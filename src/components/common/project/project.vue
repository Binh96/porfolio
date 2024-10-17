<template>
  <div class="project-container">
    <div class="project-content-container d-flex justify-center">
      <div class="project-header">
        <h3>What I've Build</h3>
      </div>
      <div class="project-body">
        <ul class="project-list">
          <div class="project-item"></div>
        </ul>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
export default {
  name: "ProjectComponent",
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
  }
}
</style>
