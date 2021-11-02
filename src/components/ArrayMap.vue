<template>
  <div>
    <h2>Map</h2>
    <p><b>Names</b></p>
    <ul>
      <li v-for="(name, key) in names" :key="key">{{ name }}</li>
    </ul>
    <p><b>Heights</b></p>
    <ul>
      <li v-for="(height, key) in heights" :key="key">{{ height }} cm</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "ArrayMap",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  computed: {
    names() {
      return this.items.map((item) => item.name);
    },
    heights() {
      return this.items.map((item) => item.height);
    },
  },
};
</script>
<style lang=""></style>
