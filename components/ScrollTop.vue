<template>
  <transition name="fade">
    <div v-show="isScroll" class="scroll-top" @click="scrollTop">
      <v-icon icon="mdi-chevron-up"></v-icon>
    </div>
  </transition>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ScrollTop",
  props: {
    isScroll: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    scrollTop(): void {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
});
</script>

<style lang="scss" scoped>
.scroll-top {
  position: fixed;
  display: flex;
  display: -webkit-flex;
  justify-content: center;
  align-items: center;
  background: #fff;
  right: 35px;
  bottom: 35px;
  height: 44px;
  width: 44px;
  border-radius: 50%;
  box-shadow: 0px 4px 24px 0px #0e1f353d;
  cursor: pointer;
  z-index: 99;
  i {
    font-size: 30px;
  }
}
</style>
