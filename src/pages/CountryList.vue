<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";

const countries = ref();
onMounted(async () => {
  const res = await axios.get("/api/countries");
  countries.value = res.data;
});
</script>

<template>
  <div>
    <h1>Country</h1>
    <div v-for="country in countries">
      <router-link
        :to="{ name: 'country', params: { countryCode: country.code.String } }"
        >{{ country.name.String }}</router-link
      >
    </div>
  </div>
</template>
