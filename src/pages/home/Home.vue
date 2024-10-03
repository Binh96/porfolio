<template>
  <div class="home-container">
    <v-container class="pt-0">
      <HeaderComponent @open="currentComponent = $event" />
    </v-container>
    <component :is="currentComponent"></component>
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
    const currentComponent = ref("");

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
