<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const props = defineProps({
  countryCode: {
    type: String,
    required: true,
  },
});
const cities = ref();
onMounted(async () => {
  const res = await axios.get("/api/countries/" + props.countryCode);
  cities.value = res.data;
});
</script>

<template>
  <div>
    <h1>
      {{ countryCode }}
    </h1>
    <div v-for="city in cities">
      <router-link
        :to="{ name: 'city', params: { cityName: city.name.String } }"
        >{{ city.name.String }}</router-link
      >
    </div>
  </div>
</template>
