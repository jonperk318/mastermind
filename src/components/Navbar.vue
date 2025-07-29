<script setup lang="ts">
import { availableLocales, loadLanguageAsync } from "~/modules/i18n";

const { t, locale } = useI18n();

async function toggleLocales() {
  // change to some real logic
  const locales = availableLocales;
  const newLocale =
    locales[(locales.indexOf(locale.value) + 1) % locales.length];
  await loadLanguageAsync(newLocale);
  locale.value = newLocale;
}
</script>

<template>
  <div
    class="navbar flex gap-4 w-screen h-24 bg-base-100 justify-center text-xl"
  >
    <RouterLink class="btn btn-ghost" to="/" :title="t('button.home')">
      Home
    </RouterLink>
    <RouterLink class="btn btn-ghost" to="/play"> Play </RouterLink>
    <RouterLink class="btn btn-ghost" to="/instructions">
      Instructions
    </RouterLink>
    <RouterLink class="btn btn-ghost" to="/stats"> Stats </RouterLink>
  </div>
</template>
