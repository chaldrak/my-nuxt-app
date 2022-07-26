<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <header class="bg-gray-900">
    <nav class="px-4 mx-auto max-w-7xl sm:px-6 lg:px-8" aria-label="Top">
      <div class="flex items-center justify-between w-full py-2 border-b border-gray-500 lg:border-none">
        <div class="flex items-center">
          <router-link to="/">
            <span class="sr-only">Workflow</span>
            <img class="w-auto h-10" src="../assets/img/logo_256_resultats.png" alt="" />
          </router-link>
          <div class="hidden ml-10 space-x-8 lg:block">
            <NuxtLink v-for="link in navigation" :key="link.name" :to="link.href" class="text-sm font-medium text-white hover:text-indigo-50">
              {{ link.name }}
            </NuxtLink>
          </div>
        </div>
        <div class="ml-10 space-x-4">
          <NuxtLink to="#" class="inline-flex items-center p-2 text-white bg-green-600 border border-transparent rounded-full shadow-sm hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500">
            <PlusSmIconOutline class="w-6 h-6" aria-hidden="true" />
          </NuxtLink>
        </div>
      </div>
      <div class="flex flex-wrap justify-center py-4 space-x-6 lg:hidden">
        <NuxtLink v-for="link in navigation" :key="link.name" :to="link.href" class="text-sm font-medium text-white hover:text-indigo-50">
          {{ link.name }}
        </NuxtLink >
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">
import { PlusSmIcon as PlusSmIconOutline } from '@heroicons/vue/outline/index'
import {PlusIcon, TrashIcon, PencilIcon, EyeIcon} from "@heroicons/vue/solid/index";

const navigation = [
  { name: "Home", href: "/" },
  // { name: "Pricing", href: "#" },
  // { name: "Docs", href: "#" },
  { name: "Posts", href: "/posts" },
];
</script>