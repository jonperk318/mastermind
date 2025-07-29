<script setup lang="ts">
const router = useRouter();
const { t } = useI18n();
useHead({
  title: () => t("not-found"),
});
</script>

<template>
  <main
    class="flex flex-col items-center px-12 h-screen w-screen text-center text-gray-700 dark:text-gray-200"
  >
    <Navbar />
    <div class="text-4xl">
      <div class="i-carbon-warning inline-block" />
    </div>
    <RouterView />
    <div>
      <button class="text-sm btn m-3" @click="router.back()">
        {{ t("button.back") }}
      </button>
    </div>
  </main>
</template>
