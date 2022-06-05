<template>
  <button class="button" @click="clicado" :disabled="desabilitado">
    <span class="icon">
      <i :class="icone"></i>
    </span>
    <span>{{ texto }}</span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  emits: ["clicado"],
  props: {
    icone: {
      type: String,
      required: true,
    },
    texto: {
      type: String,
      required: true,
    },
    desabilitado: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    clicado(): void {
      this.$emit("clicado");
    },
  },
});
</script>
