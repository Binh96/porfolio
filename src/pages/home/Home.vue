<template>
  <div class="home-container">
    <header class="header">
      <v-container class="pt-0">
        <HeaderComponent @open="currentComponent = $event" />
      </v-container>
    </header>
    <component class="component-container" :is="currentComponent"></component>
  </div>
</template>
<script lang="ts">
import { ref } from "vue";
import HeaderComponent from "../../components/common/header/header.vue";
import AboutComponent from "../../components/common/about/about.vue";
import { HomeSettingComponent } from "./home.i";
export default {
  components: {
    HeaderComponent,
    AboutComponent,
  },
  setup() {
    const currentComponent = ref(HomeSettingComponent.ABOUT_COMPONENT);

    return {
      currentComponent,
      HomeSettingComponent,
    };
  },
  methods: {
    async openComponent(name: string) {
      switch (name) {
        case HomeSettingComponent.ABOUT_COMPONENT: {
          this.currentComponent = HomeSettingComponent.ABOUT_COMPONENT;
          break;
        }
        case HomeSettingComponent.PROJECT_COMPONENT: {
          this.currentComponent = HomeSettingComponent.PROJECT_COMPONENT;
          break;
        }
        case HomeSettingComponent.EXP_COMPONENT: {
          this.currentComponent = HomeSettingComponent.EXP_COMPONENT;
          break;
        }
        case HomeSettingComponent.CONTACT_COMPONENT: {
          this.currentComponent = HomeSettingComponent.CONTACT_COMPONENT;
          break;
        }
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.home-container {
  overflow: hidden;
  height: 100%;

  .header {
    position: fixed;
    top: 0;
    right: 0;
    left: 0;
    z-index: 9999;
  }

  .component-container {
    // -top: 68px;
  }
}
</style>
