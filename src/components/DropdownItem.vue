<template>
  <div role="tabpanel" v-show="isActive">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    leftIcon: {
      required: false
    },
    rightIcon: {
      required: false
    },
    goToMenu: {
      type: String,
      required: false
    }
  }
};
</script>