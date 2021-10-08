<template>
  <!--  <button @click="onClick">test button</button>-->
  <button class="btn" @click="onClickHandler">test button</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: {
      type: String,
      required: true
    },
    // onClick: {
    //   type: Function,
    //   required: true
    // }
    onClick: {
      type: Function,
      required: false
    }
  },
  methods: {
    onClickHandler() {
      this.$emit("button-click");
    }
  }
};
</script>

<style scoped>
.btn {
  padding: 6px 10px;
  display: flex;
  background: wheat;
  align-items: center;
  justify-content: center;
  border: 2px solid black;
  text-transform: uppercase;
  font-weight: bold;
  transition: 0.2s;
  cursor: pointer;
}
.btn:hover {
  transform: scale(1.03, 1.03);
}
</style>
