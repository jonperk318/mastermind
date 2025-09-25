<script setup lang="ts">
defineOptions({
  name: "IndexPage",
});

const { t } = useI18n();
useHead({
  title: () => t("button.default"),
});
</script>

<template>
  <div>
    <div class="text-4xl">
      <div class="i-carbon-campsite inline-block" />
    </div>
    <p>
      <a
        rel="noreferrer"
        href="https://en.wikipedia.org/wiki/Mastermind_(board_game)"
        target="_blank"
      >
        Mastermind
      </a>
    </p>
    <p>
      <em class="text-sm opacity-75">The famous board game created in 1970</em>
    </p>

    <div class="py-4" />
  </div>
</template>

<route lang="yaml">
meta:
  layout: default
</route>
