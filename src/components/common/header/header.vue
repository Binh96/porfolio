<template>
  <div
    class="header-container d-flex w-100 align-center justify-space-between px-6 py-2"
  >
    <div class="logo">
      <a href="/" class="logo-title px-8">{{ logo }}</a>
    </div>
    <div class="nav-container">
      <ul class="nav-list d-flex align-center">
        <li v-for="item in navItems" :key="item?.name" class="nav-list-item">
          <ButtonComponent :content="item?.name" :isHovered="true" />
        </li>
      </ul>
    </div>
  </div>
</template>
<script lang="ts">
import { ref } from "vue";
import ButtonComponent from "../button/button.vue";
import { LOGO_TITLE, NavItemProps } from "./header.i";

import data from "../../../assets/data/user.json";

export default {
  name: "HeaderComponent",
  components: {
    ButtonComponent,
  },
  setup() {
    const logo = ref(LOGO_TITLE);
    const navItems = ref<Array<NavItemProps>>(
      (() => {
        const navItemFormat = data.navigate.map((d) => {
          return {
            name: d.name,
            link: d.dir,
            disable: false,
          } as NavItemProps;
        });
        return navItemFormat;
      })()
    );

    return {
      navItems,
      logo,
    };
  },
};
</script>
<style scoped lang="scss">
@import url("../../../styles/scss/common/base.scss");
@import "../../../styles/settings.scss";

.logo-title {
  font-size: 20px;
  color: $text-main-color;
  text-decoration: none;
}

.nav-list {
  list-style: none;

  .nav-list-item {
    color: $text-main-color;
  }
}
</style>
