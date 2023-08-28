<template>
  <div>
    <div class="text-4xl font-bold text-center pb-5 drop-shadow">
      Asmaul Husna ❤
    </div>
    <div class="grid grid-cols-2 gap-2">
      <div
        class="card w-30 bg-base-100 shadow-xl"
        v-for="asmaulHusna in asmaulHusnas"
        :key="asmaulHusna.id"
      >
        <div class="card-body text-center">
          <p class="text-5xl font-bold custom-font">{{ asmaulHusna.name }}</p>
          <p class="font-bold">{{ asmaulHusna.transliteration }}</p>
          <p>{{ asmaulHusna.en.meaning }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
// let allapidataaladhan =
//   "http://api.aladhan.com/v1/asmaAlHusna/1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,52,53,54,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,79,80,81,82,83,84,85,86,87,88,89,90,91,92,93,94,95,96,97,98,99";
// let apialadhan = "http://api.aladhan.com/v1/asmaAlHusna/1";
let apirawgithub =
  "https://raw.githubusercontent.com/Taufikhdyt17/data-json/main/asmaul_husna.json";
export default {
  data() {
    return {
      asmaulHusnas: [],
    };
  },

  methods: {
    async getData() {
      fetch(apirawgithub)
        .then((response) => response.json())
        .then((data) => (this.asmaulHusnas = data.data));
    },
  },

  mounted() {
    this.getData();
      // const response = await axios
      //   .get('http://localhost:5173/Taufikhdyt17/data-json/main/asmaul_husna.json', {
      //     headers: {
      //       "Access-Control-Allow-Origin": "*",
      //       "Access-Control-Allow-Methods": "GET,PUT,POST,DELETE,PATCH,OPTIONS",
      //     },
      //   })
      //   .then(function (response) {
      //     this.asmaulHusnas = response.data;
      //   })
      //   .catch(function (error) {
      //     console.log(error);
      //   });
  },
};
</script>
