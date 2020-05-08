<template>
  <li class="nav-item">
    <a href="#" class="icon-button" @click="toggleOpen">
      <slot></slot>
    </a>
    <dropdown-menu v-if="isOpen"></dropdown-menu>
  </li>
</template>

<script>
import DropdownMenu from "./DropdownMenu";
export default {
  components: {
    DropdownMenu
  },
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    toggleOpen() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>