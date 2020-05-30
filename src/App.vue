<template>
  <div class="flex justify-center w-screen h-screen bg-gray-100">
    <div class="relative w-full h-screen max-w-sm bg-white shadow-lg">
      <statusbar />
    </div>
  </div>
</template>

<script>
import statusbar from "@/components/_statusbar.vue";

export default {
  name: "app",
  components: {
    statusbar
  }
};
</script>

<style lang="scss" scoped></style>
