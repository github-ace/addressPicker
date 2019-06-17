<template>
  <input type="text" @click="choose" :value="value">
</template>
<script>
import "weui";
import weui from "weui.js";
import address from "./address";
console.log(address);
export default {
  props: ["value"],
  data() {
    return {
      address: address
    };
  },
  methods: {
    choose() {
      weui.picker(address, {
        defaultValue: [0, 0, 0],
        onChange: result => {
          // console.log(result);
        },
        onConfirm: result => {
          this.$emit("choose", result);
        },
        id: "multiPickerBtn"
      });
    }
  },
  mounted() {}
};
</script>
<style lang="less" scoped>
</style>
