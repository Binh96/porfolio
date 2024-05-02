<script setup>
import Layout from "../layout/Layout.vue";
</script>
<template>
  <Layout>
    <template v-slot:left-col>
      <h3>Hello! I'm Binh</h3>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum nostrum
        odit labore dolorem ipsam animi at excepturi soluta, facilis similique.
      </p>
    </template>
    <template v-slot:right-col>
      <div class="image-container">
        <MainImage/>
      </div>
    </template>
  </Layout>
</template>
<style scoped>
  .image-container{
    margin: 20px 0;
    padding: 0 150px 0 0;
  }
</style>
