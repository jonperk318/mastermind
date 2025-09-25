<script setup lang="ts">
defineOptions({
  name: "PlayPage",
});

interface PegOptions {
  id: number;
  bg: string;
}

const pegOptions: PegOptions[] = [
  { id: 1, bg: "bg-primary" },
  { id: 2, bg: "bg-secondary" },
  { id: 3, bg: "bg-accent" },
  { id: 4, bg: "bg-success" },
  { id: 5, bg: "bg-warning" },
  { id: 6, bg: "bg-info" },
  { id: 7, bg: "bg-error" },
];

class Peg {
  public id: number;
  public bg: string;

  constructor(id: number, bg: string) {
    this.id = id;
    this.bg = bg;
  }
}
</script>

<template>
  <div>The game goes here</div>
</template>

<route lang="yaml">
meta:
  layout: default
</route>
