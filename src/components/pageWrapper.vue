<template>
  <div
    class="relative w-full h-screen flex flex-col gap-4 overflow-y-auto snap-y snap-mandatory scroll-smooth"
  >
    <header-component />

    <slot />

    <footer-component class="hidden xs:flex" />

    <popup-component
    v-if="showCookies"
    @close="showCookies = false"
    class="z-50"
  />
  </div>
</template>

<script setup>
import headerComponent from "./headerComponent.vue";
import footerComponent from "./footerComponent.vue";
import popupComponent from "./ui/popup.vue";
import { useStorage } from "@vueuse/core";

const showCookies = useStorage("showCookies", true);
</script>

<style></style>
