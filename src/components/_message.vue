<template>
  <div id="__message" class="absolute w-full">
    <div class="container flex flex-col h-full pb-1 space-y-1 overflow-y-auto">
      <div
        id="__date"
        class="flex justify-center mt-2 mb-2 space-x-1 text-xs text-gray-700"
      >
        <span class="font-semibold">{{ dataHari }}</span>
        <span class="font-light">{{ dataJam }}</span>
      </div>
      <bubble
        class="capitalize"
        arah="right"
        :pesan="dataUcapan + ' ' + nama + '.'"
      />
      <bubble arah="right" pesan="Aku mau ngomong nih sama kamu.." />
      <br />
      <bubble arah="left" pesan="Ngomong apa?" :read="dataRead" />
      <br />
      <bubble arah="right" pesan="Ya.." />
      <bubble arah="right" pesan="Kita kan udah lama nih kenalnya" />
      <bubble arah="right" pesan="Aku udah tau kamu, kamu juga udah tau aku" />
      <bubble arah="right" pesan="Kamu mau gak jadi pacar aku?" />
    </div>
  </div>
</template>

<script>
import bubble from "@/components/message/_bubble.vue";
import moment from "moment";
moment.locale("id");

export default {
  name: "component.message",
  components: {
    bubble
  },
  props: {
    nama: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      dataHari: "",
      dataJam: "",
      dataUcapan: "",
      dataRead: ""
    };
  },
  created() {
    this.dataHari = moment().format("dddd");
    this.dataJam = moment()
      .add(-10, "minutes")
      .format("hh:mm");
    this.dataRead = moment()
      .add(-8, "minutes")
      .format("hh:mm");
    if (moment().format("h") > 5) this.dataUcapan = "Pagi";
    if (moment().format("h") > 12) this.dataUcapan = "Siang";
    if (moment().format("h") > 15) this.dataUcapan = "Sore";
    if (moment().format("h") > 19) this.dataUcapan = "Malem";
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
#__message {
  top: 120px;
  bottom: 135px;
}
</style>
