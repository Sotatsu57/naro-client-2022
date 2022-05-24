<script setup>
import axios from "axios";
import { ref, onMounted } from "vue";
const props = defineProps({
  cityName: {
    type: String,
    required: true,
  },
});
const cityInfo = ref();
onMounted(async () => {
  const res = await axios.get("/api/cities/" + props.cityName);
  cityInfo.value = res.data;
});
</script>

<template>
  <div>
    <h1>
      {{ cityName }}
    </h1>
    <div v-if="cityInfo">
      <p>国名コード {{ cityInfo.countryCode.String }}</p>
      <p>地域 {{ cityInfo.district.String }}</p>
      <p>人口 {{ cityInfo.population.Int64 }} 人</p>
    </div>
    <div v-else>街が見つかりませんでした</div>
  </div>
</template>
