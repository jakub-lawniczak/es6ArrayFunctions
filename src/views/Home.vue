<template>
  <div class="home">
    <h1>ES6 array functions</h1>
    <ArrayFilter :items="items" />
    <ArrayMap :items="items" />
    <ArraySome :items="items" />
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
import ArrayFilter from "@/components/ArrayFilter.vue";
import ArrayMap from "@/components/ArrayMap.vue";
import ArraySome from "@/components/ArraySome.vue";

export default {
  name: "Home",
  components: {
    ArrayFilter,
    ArrayMap,
    ArraySome,
  },
  data() {
    return {
      items: [],
    };
  },
  created() {
    axios
      .get("https://swapi.dev/api/people")
      .then((res) => (this.items = res.data.results));
  },
};
</script>
