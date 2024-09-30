<template>
  <div class="button-container">
    <v-btn
      :disabled="disabled"
      class="btn"
      @click="handleSubmit"
      :style="{
        transition: isHovered ? 'color 0.2s ease-in' : 'none !important',
      }"
    >
      {{ content }}
    </v-btn>
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
    isHovered: {
      type: Boolean,
      default: false,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
  },
  emits: ["submit"],
  setup(props, { emit }) {
    const handleSubmit = () => {
      emit("submit");
    };

    return {
      handleSubmit,
    };
  },
};
</script>
<style scoped lang="scss">
@import "../../../styles/scss/common/base.scss";

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
    color: $text-second-color !important;
  }
}

::v-deep {
  .v-btn__underlay,
  .v-btn__overlay {
    display: none !important;
  }
}
</style>
