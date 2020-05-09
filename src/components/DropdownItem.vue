<template>
  <a href="#" class="menu-item" @click="setActiveMenu">
    <span class="icon-button">
      <slot name="icon-button"></slot>
    </span>
    <slot></slot>
    <span class="icon-right">
      <slot name="icon-right"></slot>
    </span>
  </a>
</template>

<script>
export default {
  props: {
    goToMenu: {
      type: String,
      default: null,
      required: false
    }
  },
  methods: {
    setActiveMenu() {
      if (this.goToMenu !== null) {
        this.$emit("updateActiveMenu", this.goToMenu);
      }
    }
  }
};
</script>