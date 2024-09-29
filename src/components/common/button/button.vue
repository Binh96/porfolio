<template>
  <div class="button-container">
    <v-btn class="btn" @submit="handleSubmit"> {{ content }}</v-btn>
  </div>
</template>
<script lang="ts">
export default {
  name: "ButtonComponent",
  props: {
    content: {
      type: String,
      defaul: "",
    },
    onSubmit: {
      type: Function,
      default: () => {},
    },
  },
  emits: ["submit"],
  setup(props, { emit }) {
    const handleSubmit = () => {
      console.log(">>>>");
      emit("submit");
    };

    return {
      handleSubmit,
    };
  },
};
</script>
<style scoped lang="scss">
@import url("../../../styles/scss/common/base.scss");
@import url("../../../styles/settings.scss");

.btn {
  background-color: transparent !important;
  color: $text-main-color;
  box-shadow: none !important;
  border: none !important;

  &::before {
    background-color: transparent !important;
    color: transparent;
  }

  &:hover {
    background-color: transparent !important;
  }
}

::v-deep {
  .v-btn__underlay,
  .v-btn__overlay {
    display: none !important;
  }
}
</style>
