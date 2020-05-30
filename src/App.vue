<template>
  <div class="flex justify-center w-screen h-screen bg-gray-100">
    <div class="relative w-full h-screen max-w-sm bg-white shadow-lg">
      <statusbar class="z-50" />
      <topbar />
      <div id="__bottom" class="absolute bottom-0 w-full">
        <img src="@/assets/img/bottom.png" class="bg-center" />
      </div>
    </div>
  </div>
</template>

<script>
import statusbar from "@/components/_statusbar.vue";
import topbar from "@/components/_topbar.vue";

export default {
  name: "app",
  components: {
    statusbar,
    topbar
  }
};
</script>

<style lang="scss" scoped></style>
