<script setup lang="ts">
const pageCategory = ref([
  { name: '新着', path: '/' },
  { name: 'おすすめ', path: '/recipe/suggest' },
  { name: 'おまかせ一品', path: '/recipe/random' },
]);
</script>

<template>
  <div class="items-center">
    <nav class="mx-auto max-w-4xl">
      <ul class="flex gap-6 text-base sm:gap-7 sm:text-lg">
        <li
          v-for="(category, index) in pageCategory"
          :key="index"
          class="text-text-tertiary"
        >
          <NuxtLink
            :to="category.path"
            active-class="text-text-primary after:block after:h-0.5 after:w-full after:bg-accent-primary"
            exact-active-class=""
            class="flex flex-col gap-1 duration-150 hover:after:block hover:after:h-0.5 hover:after:w-full hover:after:bg-accent-primary sm:gap-1.5"
          >
            {{ category.name }}
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </div>
</template>
