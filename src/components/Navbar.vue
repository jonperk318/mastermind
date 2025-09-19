<script setup lang="ts">
import {
  AkAlignRight,
  AkCircleTriangleRight,
  AkHomeAlt1,
  AkInfo,
  AkPeopleGroup,
  AkPerson,
} from "@kalimahapps/vue-icons";
import { RouterLink } from "vue-router";
import ThemeToggle from "./ThemeToggle.vue";

const navigation = [
  { name: "Home", to: "/", icon: AkHomeAlt1 },
  { name: "Play", to: "/play", icon: AkCircleTriangleRight },
  { name: "Info", to: "/info", icon: AkInfo },
  { name: "Stats", to: "/stats", icon: AkAlignRight },
  { name: "Friends", to: "/friends", icon: AkPeopleGroup },
  { name: "Profile", to: "/profile", icon: AkPerson },
];
</script>

<template>
  <nav class="w-screen h-18 flex items-center px-8 bg-base-300 text-lg">
    <div class="w-1/4 h-full flex justify-start items-center">
      <h1 class="font-stretch-75% font-semibold text-2xl">MASTERMIND</h1>
    </div>
    <div class="w-1/2 flex justify-center items-center rounded-box gap-2">
      <div class="group" v-for="nav in navigation" :key="nav.name">
        <RouterLink class="btn btn-ghost group-hover:btn-primary" :to="nav.to">
          <component :is="nav.icon" class="text-2xl" />
          <span class="opacity-0 group-hover:opacity-100">{{ nav.name }}</span>
        </RouterLink>
      </div>
    </div>
    <div class="w-1/4 h-full flex justify-end items-center">
      <ThemeToggle />
    </div>
  </nav>
</template>
