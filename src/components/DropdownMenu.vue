<template>
  <div>
    <div class="dropdown" :style="{ height: menuHeight }" ref="dropdown-ref">
      <transition name="menu-primary" @enter="calcHeight">
        <div class="menu" v-show="activeMenu === 'main'">
          <a href="#" class="menu-item">My Profile</a>

          <a href="#" class="menu-item" @click="setActiveMenu('settings')">
            <span class="icon-button">
              <svg viewBox="0 0 512 512">
                <path
                  d="M487.4 315.7l-42.6-24.6c4.3-23.2 4.3-47 0-70.2l42.6-24.6c4.9-2.8 7.1-8.6 5.5-14-11.1-35.6-30-67.8-54.7-94.6-3.8-4.1-10-5.1-14.8-2.3L380.8 110c-17.9-15.4-38.5-27.3-60.8-35.1V25.8c0-5.6-3.9-10.5-9.4-11.7-36.7-8.2-74.3-7.8-109.2 0-5.5 1.2-9.4 6.1-9.4 11.7V75c-22.2 7.9-42.8 19.8-60.8 35.1L88.7 85.5c-4.9-2.8-11-1.9-14.8 2.3-24.7 26.7-43.6 58.9-54.7 94.6-1.7 5.4.6 11.2 5.5 14L67.3 221c-4.3 23.2-4.3 47 0 70.2l-42.6 24.6c-4.9 2.8-7.1 8.6-5.5 14 11.1 35.6 30 67.8 54.7 94.6 3.8 4.1 10 5.1 14.8 2.3l42.6-24.6c17.9 15.4 38.5 27.3 60.8 35.1v49.2c0 5.6 3.9 10.5 9.4 11.7 36.7 8.2 74.3 7.8 109.2 0 5.5-1.2 9.4-6.1 9.4-11.7v-49.2c22.2-7.9 42.8-19.8 60.8-35.1l42.6 24.6c4.9 2.8 11 1.9 14.8-2.3 24.7-26.7 43.6-58.9 54.7-94.6 1.5-5.5-.7-11.3-5.6-14.1zM256 336c-44.1 0-80-35.9-80-80s35.9-80 80-80 80 35.9 80 80-35.9 80-80 80z"
                  class
                />
              </svg>
            </span>
            Settings
            <span class="icon-right">
              <svg viewBox="0 0 256 512">
                <path
                  d="M24.707 38.101L4.908 57.899c-4.686 4.686-4.686 12.284 0 16.971L185.607 256 4.908 437.13c-4.686 4.686-4.686 12.284 0 16.971L24.707 473.9c4.686 4.686 12.284 4.686 16.971 0l209.414-209.414c4.686-4.686 4.686-12.284 0-16.971L41.678 38.101c-4.687-4.687-12.285-4.687-16.971 0z"
                  class
                />
              </svg>
            </span>
          </a>

          <a href="#" class="menu-item" @click="setActiveMenu('animals')">
            <span class="icon-button">🦧</span>
            Animals
            <span class="icon-right">
              <svg viewBox="0 0 256 512">
                <path
                  d="M24.707 38.101L4.908 57.899c-4.686 4.686-4.686 12.284 0 16.971L185.607 256 4.908 437.13c-4.686 4.686-4.686 12.284 0 16.971L24.707 473.9c4.686 4.686 12.284 4.686 16.971 0l209.414-209.414c4.686-4.686 4.686-12.284 0-16.971L41.678 38.101c-4.687-4.687-12.285-4.687-16.971 0z"
                  class
                />
              </svg>
            </span>
          </a>
        </div>
      </transition>

      <transition name="menu-secondary" @enter="calcHeight">
        <div class="menu" v-show="activeMenu === 'settings'">
          <a href="#" class="menu-item" @click="setActiveMenu('main')">
            <span class="icon-button">
              <svg viewBox="0 0 448 512">
                <path
                  fill="currentColor"
                  d="M257.5 445.1l-22.2 22.2c-9.4 9.4-24.6 9.4-33.9 0L7 273c-9.4-9.4-9.4-24.6 0-33.9L201.4 44.7c9.4-9.4 24.6-9.4 33.9 0l22.2 22.2c9.5 9.5 9.3 25-.4 34.3L136.6 216H424c13.3 0 24 10.7 24 24v32c0 13.3-10.7 24-24 24H136.6l120.5 114.8c9.8 9.3 10 24.8.4 34.3z"
                  class
                />
              </svg>
            </span>
            <h2>Skills</h2>
          </a>
          <a href="#" class="menu-item">
            <span class="icon-button">
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </span>
            HTML
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </span>
            CSS
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </span>
            Javascript
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">
              <svg viewBox="0 0 320 512">
                <path
                  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"
                  class
                />
              </svg>
            </span>
            Awesome
          </a>
        </div>
      </transition>

      <transition name="menu-secondary" @enter="calcHeight">
        <div class="menu" v-show="activeMenu === 'animals'">
          <a href="#" class="menu-item" @click="setActiveMenu('main')">
            <span class="icon-button">
              <svg viewBox="0 0 448 512">
                <path
                  fill="currentColor"
                  d="M257.5 445.1l-22.2 22.2c-9.4 9.4-24.6 9.4-33.9 0L7 273c-9.4-9.4-9.4-24.6 0-33.9L201.4 44.7c9.4-9.4 24.6-9.4 33.9 0l22.2 22.2c9.5 9.5 9.3 25-.4 34.3L136.6 216H424c13.3 0 24 10.7 24 24v32c0 13.3-10.7 24-24 24H136.6l120.5 114.8c9.8 9.3 10 24.8.4 34.3z"
                  class
                />
              </svg>
            </span>

            <h2>Animals</h2>
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">🦘</span>
            Kangaroo
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">🐸</span>
            Frog
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">🦋</span>
            Butterfly
          </a>

          <a href="#" class="menu-item">
            <span class="icon-button">🦔</span>
            Hedgehog
          </a>
        </div>
      </transition>
    </div>
  </div>
</template>

<script>
export default {
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