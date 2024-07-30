<script setup lang="ts">
const { data: pokedata } = await useFetch("https://pokeapi.co/api/v2/pokemon");
const pokemons = pokedata.value.results;
console.log(pokedata.value.results[0].name);
</script>
<template>
  <div>
    <ul id="example-1">
      <li v-for="item in pokemons" :key="item.name">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>
