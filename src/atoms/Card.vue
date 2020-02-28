<template>
  <div class="card" @click="onCountryClick(data.name)">
    <div class="card-image">
      <figure class="image is-3by2">
        <img :src="data.flag" :alt="data.name" />
      </figure>
    </div>
    <div class="card-content">
      <div class="content">
        <h3>{{ data.name }}</h3>
        <p><strong>Population:</strong> {{ data.population }}</p>
        <p><strong>Region:</strong> {{ data.region }}</p>
        <p><strong>Capital:</strong> {{ data.capital }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: Object
  },
  methods: {
    onCountryClick(name) {
      this.$router.push({
        name: "Country",
        params: {
          name,
          fullText: true
        }
      });
    }
  }
};
</script>
