<template>
  <header class="">
    <v-container>
      <v-row class="header-container">
        <v-col>
          <div class="logo">
            <h3>Binh Phan</h3>
          </div>
        </v-col>
        <v-col>
          <v-list :class="['pd-xy-0', 'navigation-list']">
            <v-list-item v-for="item in navigate" :key="item">
              <a href="">{{ item.name }}</a>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-container>
  </header>
</template>
<script lang="ts">
import userData from "../../assets/data/user.json";
export default {
  data() {
    return {
      navigate: [],
      data: JSON.stringify(userData["navigate"]),
    };
  },
  mounted() {
    this.navigate = JSON.parse(this.data);
  },
};
</script>
<style scoped lang="scss">
@import "../../styles/scss/common/base.scss";

header {
  position: fixed;
  width: 100%;

  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;

    .navigation-list {
      display: flex;
      justify-content: end;
      background-color: $bg-main-color;
    }
  }
}
</style>
