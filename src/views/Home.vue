<template>
  <div class="flex flex-col p-8">
    <div>
      <input
        type="text"
        class="rounded border-2 border-gray-200 w-full"
        placeholder="Search for a meal"
      />
    </div>

    <div class="flex justify-center gap-2 mt-2">
      <router-link
        v-for="letter in letters"
        :key="letter"
        :to="{ name: 'byletter', params: { letter } }"
        class="text-xl"
        >{{ letter }}</router-link
      >
    </div>
  </div>
</template>

<script setup>
import { computed, onMounted } from "vue";
import store from "../store/index.js";
import axios from "../axiosClient.js";

const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
onMounted(async () => {
    const response = await axios.get("/list.php?i=list")
    console.log(response.data)
})
</script>
