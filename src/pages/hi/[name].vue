<script setup lang="ts">
const router = useRouter();
const route = useRoute("/hi/[name]");
const user = useUserStore();
const { t } = useI18n();

watchEffect(() => {
  user.setNewName(route.params.name);
});
useHead({
  title: () => t("intro.hi", { name: user.savedName }),
});
</script>

<template>
  <div>
    <div class="text-4xl">
      <div class="i-carbon-pedestrian inline-block" />
    </div>
    <p>
      {{ t("intro.hi", { name: user.savedName }) }}
    </p>

    <p class="text-sm opacity-75">
      <em>{{ t("intro.dynamic-route") }}</em>
    </p>

    <template v-if="user.otherNames.length">
      <div class="mt-4 text-sm">
        <span class="opacity-75">{{ t("intro.aka") }}:</span>
        <ul>
          <li v-for="otherName in user.otherNames" :key="otherName">
            <RouterLink :to="`/hi/${otherName}`" replace>
              {{ otherName }}
            </RouterLink>
          </li>
        </ul>
      </div>
    </template>

    <div>
      <button class="m-3 m-t6 text-sm btn" @click="router.back()">
        {{ t("button.back") }}
      </button>
    </div>
  </div>
</template>
