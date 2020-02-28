<template>
  <section class="section">
    <div class="container">
      <div class="field is-horizontal">
        <div class="field-body">
          <div class="control">
            <input
              class="input"
              type="text"
              placeholder="&#xF002; Search for country..."
            />
          </div>
          <Dropdown />
        </div>
      </div>
      <div class="columns is-multiline">
        <div v-for="(item, index) in info" class="column is-3" :key="index">
          <Card :data="item" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from "axios";
import Dropdown from "@/atoms/Dropdown.vue";
import Card from "@/atoms/Card.vue";

export default {
  components: {
    Dropdown,
    Card
  },
  data() {
    return {
      info: []
    };
  },
  mounted() {
    axios
      .get("https://restcountries.eu/rest/v2/all")
      .then(response => (this.info = response.data))
      .catch(error => console.error(error));
  }
};
</script>

<style lang="scss" scoped>
.field-body {
  justify-content: space-between;
}
</style>
