<template>
  <div>
    <v-btn
      v-if="variant === 'outlined'"
      :append-icon="`${appendIcon}`"
      :prepend-icon="`${preIcon}`"
      variant="outlined"
      @click="btnClick"
      :disabled="disabled"
      class="btn-outlined"
      size="large"
    >
      {{ label }}
    </v-btn>
    <v-btn
      v-if="variant === 'text'"
      :append-icon="`${appendIcon}`"
      :prepend-icon="`${preIcon}`"
      variant="text"
      @click="btnClick"
      :disabled="disabled"
      class="btn-text"
      size="large"
    >
      {{ label }}
    </v-btn>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Button",
  props: {
    label: {
      type: String,
      default: "",
    },
    appendIcon: {
      type: String,
      default: "",
    },
    preIcon: {
      type: String,
      default: "",
    },
    variant: {
      type: String,
      default: "outlined",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    isNone: {
      type: Boolean,
      default: false,
    },
  },
  emits: ["btnClick"],
  methods: {
    btnClick(): void {
      this.$emit("btnClick");
    },
  },
});
</script>

<style lang="scss" scoped>
@use "@/public/scss/abstracts/global" as *;
.btn-outlined {
  text-transform: none;
  background-color: #ffffff;
  border: 1px solid #e63946;
  color: #e63946;
  font-size: 15px;
  font-weight: 500;
  display: flex;
  justify-content: center;
  align-items: center;
}
.btn-text {
  text-transform: none;
  background-color: #e63946;
  color: #ffffff;
  font-size: 15px;
  font-weight: 500;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
