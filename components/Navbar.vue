<template>
  <div class="navbar" :class="{ scroll: isScroll }">
    <div class="navbar__container">
      <div class="navbar-logo">
        <div>Raihan</div>
        <div></div>
      </div>
      <div class="navbar-items">
        <ul>
          <li @click="handleClickProjects">Projects</li>
          <li @click="handleClickContact">Contact</li>
        </ul>
      </div>
      <div class="hamburger-menu">
        <v-icon
          id="menu-dropdown"
          :icon="showMobileMenu ? 'mdi-close' : 'mdi-menu'"
          @click="showMenu"
        ></v-icon>
        <div
          id="list-dropdown"
          class="nav-content"
          :class="showMobileMenu ? 'open-menu' : 'closed-menu'"
        >
          <div class="wrapper-menu">
            <ul class="nav-items">
              <li @click="handleClickProjects">Projects</li>
              <li @click="handleClickContact">Contact</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
export default defineComponent({
  name: "Navbar",
  data() {
    return {
      isScroll: false,
      showMobileMenu: false,
    };
  },
  emits: ["clickProjects", "clickContact"],
  mounted() {
    window.addEventListener("scroll", this.doScroll);
    window.addEventListener("click", () => {
      const vxAvatarDropdown = document.getElementById("list-dropdown");
      const vxAvatar = document.getElementById("menu-dropdown");
      window.addEventListener("click", (e) => {
        const isContainsAvatarDropdown = vxAvatarDropdown?.contains(
          e.target as Node
        );
        const isContainsAvatar = vxAvatar?.contains(e.target as Node);
        if (!isContainsAvatarDropdown && !isContainsAvatar) {
          this.showMobileMenu = false;
        }
      });
    });
  },
  unmounted() {
    window.removeEventListener("scroll", this.doScroll);
  },
  methods: {
    handleClickProjects(): void {
      if (this.showMobileMenu) {
        this.showMobileMenu = false;
      }
      this.$emit("clickProjects");
    },
    handleClickContact(): void {
      if (this.showMobileMenu) {
        this.showMobileMenu = false;
      }
      this.$emit("clickContact");
    },
    doScroll() {
      if (window.scrollY > 50) {
        this.isScroll = true;
      } else {
        this.isScroll = false;
      }
    },
    showMenu() {
      this.showMobileMenu = !this.showMobileMenu;
    },
  },
});
</script>

<style lang="scss" scoped>
@use "@/public/scss/abstracts/global" as *;

.navbar {
  background-color: #ffffff;
  top: 0;
  left: 0;
  right: 0;
  position: fixed;
  z-index: 1000000;
  &__container {
    max-width: $max-width;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    padding: 20px;
    .navbar-logo {
      font-family: "Raleway";
      font-style: normal;
      font-weight: 700;
      font-size: 38px;
      line-height: 25px;
      color: #2d2d2d;
      display: flex;
      align-items: flex-end;
      gap: 3px;
      cursor: pointer;
      div {
        &:nth-child(2) {
          background: #e63946;
          width: 8px;
          height: 8px;
          border-radius: 99px;
        }
      }
    }
    .navbar-items {
      ul {
        display: flex;
        justify-content: center;
        align-items: center;
        list-style: none;
        height: 100%;
        margin: 0;
        padding: 0;
        color: #6b7280;
        gap: 30px;
        font-family: "Neutral Face";
        font-style: normal;
        font-weight: 400;
        font-size: 20px;
        li {
          padding: 0 10px;
          cursor: pointer;
          border-bottom: 1px solid #ffffff;

          &:hover,
          &:active {
            color: #e63946;
            border-bottom: 1px solid #e63946;
          }
        }
      }
    }

    .hamburger-menu {
      display: none;
    }
  }
}

.scroll {
  box-shadow: 0 4px 2px -2px rgba(14, 31, 53, 0.08);
}

@media (max-width: $max-width-mobile) {
  .navbar {
    &__container {
      .navbar-logo {
        font-size: 35px;
      }
      .navbar-items {
        display: none;
      }

      .hamburger-menu {
        display: block;
        position: relative;

        i {
          position: absolute;
          right: 0;
        }
        .nav-content {
          position: absolute;
          top: 50px;
          right: 0;
          box-shadow: 0px 2px 10px rgba(14, 31, 53, 0.08);
          background: #ffffff;
          z-index: 100;
          padding: 20px;
          transition: all 0.2s ease-out;
          border-radius: 5px;
          visibility: visible;

          .wrapper-menu {
            .nav-items {
              flex-direction: column;
              display: flex;
              justify-content: center;
              align-items: center;
              list-style: none;
              height: 100%;
              margin: 0;
              padding: 0 20px;
              gap: 30px;
              li {
                padding: 0 10px;
                font-family: "Neutral Face";
                font-style: normal;
                font-weight: 400;
                font-size: 20px;
                color: #6b7280;

                &:hover,
                &:active {
                  color: #e63946;
                  border-bottom: 1px solid #e63946;
                }
              }
            }
          }
        }
        .open-menu {
          opacity: 1;
        }
        .closed-menu {
          opacity: 0;
          height: 0;
          padding: 0;
          visibility: hidden;
        }
      }
    }
  }
}
</style>
