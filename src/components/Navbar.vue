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
  <nav class="w-screen h-18 flex items-center px-8 bg-base-100 text-lg">
    <div class="w-1/2 h-full flex justify-start items-center">
      <div>LOGO</div>
    </div>
    <div
      class="h-2/3 flex justify-end items-center rounded-box gap-2 border-4 border-neutral"
    >
      <div class="group" v-for="nav in navigation" :key="nav.name">
        <RouterLink class="btn btn-ghost group-hover:btn-primary" to="nav.to">
          <component :is="nav.icon" class="mr-2 text-2xl" />
          <span class="opacity-0 group-hover:opacity-100">{{ nav.name }}</span>
        </RouterLink>
      </div>
    </div>
  </nav>
</template>
