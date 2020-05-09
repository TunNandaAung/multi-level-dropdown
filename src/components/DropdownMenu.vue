<template>
  <div>
    <div class="dropdown" :style="{ height: menuHeight }" ref="dropdown-ref">
      <transition name="menu-primary" @afterEnter="calcHeight">
        <div class="menu" v-show="activeMenu === 'main'">
          <a href="#" class="menu-item">My Profile</a>

          <dropdown-item @updateActiveMenu="setActiveMenu" goToMenu="settings">
            <template v-slot:icon-button>
              <svg viewBox="0 0 512 512">
                <path
                  d="M487.4 315.7l-42.6-24.6c4.3-23.2 4.3-47 0-70.2l42.6-24.6c4.9-2.8 7.1-8.6 5.5-14-11.1-35.6-30-67.8-54.7-94.6-3.8-4.1-10-5.1-14.8-2.3L380.8 110c-17.9-15.4-38.5-27.3-60.8-35.1V25.8c0-5.6-3.9-10.5-9.4-11.7-36.7-8.2-74.3-7.8-109.2 0-5.5 1.2-9.4 6.1-9.4 11.7V75c-22.2 7.9-42.8 19.8-60.8 35.1L88.7 85.5c-4.9-2.8-11-1.9-14.8 2.3-24.7 26.7-43.6 58.9-54.7 94.6-1.7 5.4.6 11.2 5.5 14L67.3 221c-4.3 23.2-4.3 47 0 70.2l-42.6 24.6c-4.9 2.8-7.1 8.6-5.5 14 11.1 35.6 30 67.8 54.7 94.6 3.8 4.1 10 5.1 14.8 2.3l42.6-24.6c17.9 15.4 38.5 27.3 60.8 35.1v49.2c0 5.6 3.9 10.5 9.4 11.7 36.7 8.2 74.3 7.8 109.2 0 5.5-1.2 9.4-6.1 9.4-11.7v-49.2c22.2-7.9 42.8-19.8 60.8-35.1l42.6 24.6c4.9 2.8 11 1.9 14.8-2.3 24.7-26.7 43.6-58.9 54.7-94.6 1.5-5.5-.7-11.3-5.6-14.1zM256 336c-44.1 0-80-35.9-80-80s35.9-80 80-80 80 35.9 80 80-35.9 80-80 80z"
                  class
                />
              </svg>
            </template>
            Settings
            <template v-slot:icon-right>
              <img src="../assets/icons/chevron.svg" />
            </template>
          </dropdown-item>

          <dropdown-item @updateActiveMenu="setActiveMenu" goToMenu="animals">
            <template v-slot:icon-button>🦧</template>
            Animals
            <template v-slot:icon-right>
              <img src="../assets/icons/chevron.svg" />
            </template>
          </dropdown-item>
        </div>
      </transition>

      <transition name="menu-secondary" @afterEnter="calcHeight">
        <div class="menu" v-show="activeMenu === 'settings'">
          <dropdown-item goToMenu="main" @updateActiveMenu="setActiveMenu">
            <template v-slot:icon-button>
              <svg viewBox="0 0 448 512">
                <path
                  fill="currentColor"
                  d="M257.5 445.1l-22.2 22.2c-9.4 9.4-24.6 9.4-33.9 0L7 273c-9.4-9.4-9.4-24.6 0-33.9L201.4 44.7c9.4-9.4 24.6-9.4 33.9 0l22.2 22.2c9.5 9.5 9.3 25-.4 34.3L136.6 216H424c13.3 0 24 10.7 24 24v32c0 13.3-10.7 24-24 24H136.6l120.5 114.8c9.8 9.3 10 24.8.4 34.3z"
                  class
                />
              </svg>
            </template>
            <slot>
              <h2>Skills</h2>
            </slot>
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </template>
            HTML
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </template>
            CSS
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </template>
            Javascript
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </template>
            Awesome
          </dropdown-item>
        </div>
      </transition>

      <transition name="menu-secondary" @afterEnter="calcHeight">
        <div class="menu" v-show="activeMenu === 'animals'">
          <dropdown-item goToMenu="main" @updateActiveMenu="setActiveMenu">
            <template v-slot:icon-button>
              <svg viewBox="0 0 448 512">
                <path
                  fill="currentColor"
                  d="M257.5 445.1l-22.2 22.2c-9.4 9.4-24.6 9.4-33.9 0L7 273c-9.4-9.4-9.4-24.6 0-33.9L201.4 44.7c9.4-9.4 24.6-9.4 33.9 0l22.2 22.2c9.5 9.5 9.3 25-.4 34.3L136.6 216H424c13.3 0 24 10.7 24 24v32c0 13.3-10.7 24-24 24H136.6l120.5 114.8c9.8 9.3 10 24.8.4 34.3z"
                  class
                />
              </svg>
            </template>

            <h2>Animals</h2>
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>🦘</template>
            Kangaroo
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>🐸</template>
            Frog
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>🦋</template>
            Butterfly
          </dropdown-item>

          <dropdown-item>
            <template v-slot:icon-button>🦔</template>
            Hedgehog
          </dropdown-item>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
import DropdownItem from "./DropdownItem";

export default {
  components: {
    DropdownItem
  },
  data() {
    return {
      activeMenu: "main",
      menuHeight: null,
      items: []
    };
  },
  mounted() {
    this.items = this.$children;
    //this.setInitialActiveTab();
  },
  watch: {
    menuHeight() {
      this.setMenuHeight(
        this.$refs["dropdown-ref"].current?.firstChild.offsetHeight
      );
    }
  },
  methods: {
    setActiveMenu(activeMenu) {
      this.activeMenu = activeMenu;
    },
    setMenuHeight(height) {
      this.menuHeight = height;
    },
    calcHeight(el) {
      const height = el.offsetHeight;
      this.setMenuHeight(height);
    }
  }
};
</script>