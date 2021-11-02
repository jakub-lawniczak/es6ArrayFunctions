<template>
  <div>
    <h2>Filter</h2>
    <p><b>Male characters</b></p>
    <ul>
      <li v-for="(item, key) in male" :key="key">{{ item.name }}</li>
    </ul>
    <p><b>Female characters</b></p>
    <ul>
      <li v-for="(item, key) in female" :key="key">{{ item.name }}</li>
    </ul>
    <p><b>Short characters</b></p>
    <ul>
      <li v-for="(item, key) in short" :key="key">
        {{ item.name }} : {{ item.height }} cm
      </li>
    </ul>
    <p><b>Tall characters</b></p>
    <ul>
      <li v-for="(item, key) in tall" :key="key">
        {{ item.name }} : {{ item.height }} cm
      </li>
    </ul>
    <p><b>Brown Eye Color</b></p>
    <ul>
      <li v-for="(item, key) in bronwEyeColor" :key="key">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "ArrayFilter",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
  computed: {
    male() {
      return this.items.filter((item) => item.gender === "male");
    },
    female() {
      return this.items.filter((item) => item.gender === "female");
    },
    short() {
      return this.items.filter((item) => item.height <= 170);
    },
    tall() {
      return this.items.filter((item) => item.height > 170);
    },
    bronwEyeColor() {
      return this.items.filter((item) => item.eye_color === "brown");
    },
  },
};
</script>
