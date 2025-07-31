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
  <div class="w-screen h-18 flex px-8 bg-base-100 text-lg">
    <div class="w-1/2 h-full flex justify-start items-center">
      <div>LOGO</div>
    </div>
    <div
      class="w-1/2 h-full flex justify-end items-center"
      v-for="nav in navigation"
      :key="nav.name"
    >
      <RouterLink class="btn btn-ghost btn-sm" to="nav.to">
        <component :is="nav.icon" class="mr-2 text-xl" />{{ nav.name }}
      </RouterLink>
    </div>
  </div>
</template>
