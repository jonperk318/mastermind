<script setup lang="ts">
defineOptions({
  name: "IndexPage",
});
const user = useUserStore();
const name = ref(user.savedName);

const router = useRouter();
function go() {
  if (name.value) router.push(`/hi/${encodeURIComponent(name.value)}`);
}

const { t } = useI18n();
useHead({
  title: () => t("button.home"),
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
  layout: home
</route>
