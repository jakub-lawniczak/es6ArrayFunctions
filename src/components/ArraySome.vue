<template>
  <div>
    <h2>Some</h2>
    <p>
      some user from api have blue eyes?...<b>{{ blueEyes }}</b>
    </p>

    <p>
      some user from api have pink eyes?...<b>{{ pinkEyes }}</b>
    </p>
  </div>
</template>
<script>
export default {
  name: "ArraySome",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  computed: {
    blueEyes() {
      return this.items.some((item) => item.eye_color === "blue");
    },
    pinkEyes() {
      return this.items.some((item) => item.eye_color === "pink");
    },
  },
};
</script>
<style lang=""></style>
