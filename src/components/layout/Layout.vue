<template>
  <div class="layout-flex">
    <v-container class="layout-container">
      <v-row>
        <v-col class="pd-xy-0">
          <slot name="left-col" />
        </v-col>
        <v-col class="pd-xy-0">
          <slot name="right-col" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<style scoped>
@import "../../styles/scss/common/base.scss";

.layout-flex,
.layout-container,
.v-row {
  height: 100vh;

  &.layout-container {
  }

  &.v-row {
    align-items: center;
  }
}
</style>
