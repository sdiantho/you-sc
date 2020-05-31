<template>
  <div class="flex justify-center w-screen h-screen bg-gray-100">
    <div class="relative w-full h-screen max-w-sm bg-white shadow-lg">
      <statusbar class="z-30 select-none" />
      <topbar class="z-20 select-none" />
      <message :nama="nama" v-if="!notifikasi" />
      <div id="__bottom" class="absolute bottom-0 w-full select-none">
        <img src="@/assets/img/bottom.png" class="bg-center" />
      </div>

      <!-- notifikasi -->
      <div
        v-if="notifikasi"
        id="__notifikasi"
        class="absolute top-0 left-0 z-40 w-full h-full bg-black bg-opacity-75 select-none"
      >
        <div class="container flex items-center justify-center h-full">
          <div
            id="__box"
            class="flex flex-col px-5 pt-6 space-y-3 leading-none text-center"
          >
            <h2 class="text-2xl">Pemberitahuan</h2>
            <span class="text-base">
              Masukkin nama kamu – saya boleh manggil kamu apa ?
            </span>
            <input
              type="text"
              class="focus:outline-none w-full p-2 placeholder-gray-400 rounded-sm"
              placeholder="Nama panggilan"
              autofocus
              v-model="nama"
              @keyup.enter="handleNama"
            />
            <br />
            <button
              id="__btnCTA"
              class="focus:outline-none focus:text-blue-800 py-4 -mx-5 text-lg font-medium text-blue-700 border-t border-gray-700 border-opacity-25 select-none"
              @click="handleNama"
            >
              OK
            </button>
          </div>
        </div>
      </div>
      <!-- notifikasi end -->
    </div>
  </div>
</template>

<script>
import statusbar from "@/components/_statusbar.vue";
import topbar from "@/components/_topbar.vue";
import message from "@/components/_message.vue";

export default {
  name: "app",
  components: {
    statusbar,
    topbar,
    message
  },

  data() {
    return {
      notifikasi: true,
      nama: ""
    };
  },

  methods: {
    handleNama() {
      this.notifikasi = false;
    }
  }
};
</script>

<style lang="scss" scoped>
#__notifikasi {
  backdrop-filter: blur(2.5px);

  #__box {
    backdrop-filter: blur(54.37px);
    background-color: rgba($color: #f8f8f8, $alpha: 0.82);
    border-radius: 14px;

    h2 {
      letter-spacing: -0.0241176em;
      font-weight: 600;
    }

    span {
      letter-spacing: -0.00615385em;
      font-weight: 400;
    }

    input {
      border: 0.5px solid #8e8e93;
    }
  }
}
</style>
