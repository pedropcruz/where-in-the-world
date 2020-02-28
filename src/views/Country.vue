<template>
  <div class="container">
    <section class="section">
      <router-link to="/" class="button">Back</router-link>
      <div class="columns">
        <div class="column is-6">
          <figure><img :src="info.flag" :alt="info.name" /></figure>
        </div>
        <div class="column is-6">
          <div class="content">
            <h3>{{ info.name }}</h3>
            <div class="columns">
              <div class="column is-6">
                <div class="content">
                  <p><strong>Native Name:</strong> {{ info.nativeName }}</p>
                  <p><strong>Population:</strong> {{ info.population }}</p>
                  <p><strong>Region:</strong> {{ info.region }}</p>
                  <p><strong>Sub Region:</strong> {{ info.subregion }}</p>
                  <p><strong>Capital:</strong> {{ info.capital }}</p>
                </div>
              </div>
              <div class="column is-6">
                <div class="content">
                  <p>
                    <strong>Top Level Domain:</strong>
                    {{
                      info.topLevelDomain &&
                        info.topLevelDomain.map(item => item).join(",")
                    }}
                  </p>
                  <p>
                    <strong>Currencies:</strong>
                    {{
                      info.currencies &&
                        info.currencies.map(({ code }) => code).join(",")
                    }}
                  </p>
                  <p>
                    <strong>Languages:</strong>
                    {{
                      info.languages &&
                        info.languages.map(({ name }) => name).join(",")
                    }}
                  </p>
                </div>
              </div>
            </div>
            <p>
              <strong>Border Countries:</strong>
              {{ info.borders.map(item => item).join(",") }}
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      info: []
    };
  },
  created() {
    this.fetchCountry();
  },
  methods: {
    fetchCountry() {
      axios
        .get(
          `https://restcountries.eu/rest/v2/name/${this.$route.params.name}?fullText=true`
        )
        .then(response => (this.info = response.data[0]))
        .catch(error => console.log(error));
    }
  }
};
</script>
