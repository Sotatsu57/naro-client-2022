<script setup>
import axios from "axios";
const sendGet = () => axios.get("https://eouaqhcreaa6rsh.m.pipedream.net");
const sendPost = () =>
  axios.post("https://eouaqhcreaa6rsh.m.pipedream.net", {
    traQID: "temma",
    grade: 19,
  });
const sendPut = () =>
  axios.put("https://eouaqhcreaa6rsh.m.pipedream.net", {
    testData: { string: "string", number: 1 },
  });
const sendDelete = () =>
  axios.delete("https://eouaqhcreaa6rsh.m.pipedream.net", {
    data: { po: 1 },
  });
</script>
<template>
  <div>
    <button @click="sendGet">GET</button>
    <button @click="sendPost">POST</button>
    <button @click="sendPut">PUT</button>
    <button @click="sendDelete">DELETE</button>
  </div>
</template>
