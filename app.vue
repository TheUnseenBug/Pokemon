<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";
import { PokemonClient } from "pokenode-ts";
const pokemonApi = async () => {
  const api = new PokemonClient();

  const pop = await api.listPokemons(1, 151).then((data) => {
    return data;
  });
  console.log(pop);

  return pop;
};
console.log(pokemonApi);
</script>
<template>
  <div>
    <Button>Button</Button>
    <Card v-for="item in pokemons" :key="item.name">
      <CardHeader>
        <CardTitle>{{ item.name }}</CardTitle>
        <CardDescription>Card Description</CardDescription>
      </CardHeader>
      <CardContent> Card Content </CardContent>
      <CardFooter> Card Footer </CardFooter>
    </Card>
  </div>
</template>
