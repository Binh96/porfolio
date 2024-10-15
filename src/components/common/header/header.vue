<template>
  <div
    class="header-container d-flex w-100 align-center justify-space-between py-2"
  >
    <div class="logo">
      <a href="/" class="logo-title">{{ logo }}</a>
    </div>
    <div class="nav-container">
      <ul class="nav-list d-flex align-center">
        <li v-for="item in navItems" :key="item?.name" class="nav-list-item">
          <ButtonComponent
            :content="item?.name"
            :isHovered="true"
            @submit="openComponent(item.nameComponent)"
          />
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
  emits: ["open"],
  setup(props, { emit }) {
    const logo = ref(LOGO_TITLE);
    const navItems = ref<Array<NavItemProps>>(
      (() => {
        const navItemFormat = data.navigate.map((d) => {
          return {
            name: d.name,
            link: d.dir,
            disable: false,
            nameComponent: d.nameComponent,
          } as NavItemProps;
        });
        return navItemFormat;
      })()
    );

    const openComponent = (name: string) => {
      emit("open", name); // Emit the event properly
    };

    return {
      openComponent,
      navItems,
      logo,
    };
  },
  methods: {},
};
</script>
<style scoped lang="scss">
@import url("../../../styles/scss/common/base.scss");
@import "../../../styles/settings.scss";

.header-container {
  position: relative;
  top: 0;
  right: 0;
  left: 0;
  z-index: 9999;

  .logo-title {
    font-size: 20px;
    color: $text-main-color;
    text-decoration: none;
    font-weight: 600;
  }

  .nav-list {
    list-style: none;

    .nav-list-item {
      color: $text-main-color;
    }
  }
}
</style>
