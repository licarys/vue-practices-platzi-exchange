<template>
  <button
    @click="buttonClick"
    class="
      bg-transparent
      hover:bg-green-500
      text-green-700
      font-semibold
      hover:text-white
      py-2
      px-2
      border border-green-500
      hover:border-transparent
      rounded
    "
  >
    <beat-loader :loading="isLoading" :color="color" :size="8"></beat-loader>
    <p v-show="!isLoading">
      <slot></slot>
    </p>
  </button>
</template>

<script>
export default {
  name: "PxButton",

  props: {
    isLoading: {
      type: Boolean,
      default: false,
    },
  },

  data() {
    return {
      color: "#68d391",
    };
  },

  methods: {
    buttonClick() {
      this.$emit("click");
    },
  },
};
</script>
