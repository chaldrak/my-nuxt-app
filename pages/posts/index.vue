<template>
  <div class="w-11/12 mx-auto my-10">
    <div class="-mx-4 -my-2 overflow-x-auto sm:-mx-6 lg:-mx-0">
      <div class="inline-block min-w-full py-2 align-middle md:px-6 lg:px-8">
        <div class="overflow-hidden shadow ring-1 ring-black ring-opacity-5 md:rounded-lg">
          <table class="min-w-full divide-y divide-gray-300">
            <thead class="bg-gray-50">
              <tr>
                <th scope="col" class="py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 sm:pl-6">N°</th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">User</th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">Title</th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900">Status</th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"></th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"></th>
                <th scope="col" class="px-3 py-3.5 text-left text-sm font-semibold text-gray-900"></th>
              </tr>
            </thead>
            <tbody class="bg-white divide-y divide-gray-200">
              <tr v-for="post in posts" :key="post.id">
                <td class="py-4 pl-6 text-sm text-gray-500 whitespace-nowrap">
                  <div class="text-gray-900">{{ post.id }}</div>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-nowrap">
                  <div class="text-gray-900">{{ post.userId }}</div>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-wrap">
                  <div class="text-gray-900">{{ post.title }}</div>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-nowrap">
                  <span class="inline-flex px-2 text-xs font-semibold leading-5 rounded-full" :class="post.completed ? 'text-green-800 bg-green-100' : 'text-red-800 bg-red-100'">{{ post.completed ? "Completed" : "In progress" }}</span>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-nowrap">
                    <NuxtLink :to="'/posts/'+post.id" class="inline-flex items-center text-indigo-600 hover:text-indigo-700">
                      <EyeIcon class="w-4 h-4" aria-hidden="true" />
                    </NuxtLink>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-nowrap">
                  <NuxtLink to="#" class="inline-flex items-center text-green-600 hover:text-green-700">
                    <PencilIcon class="w-4 h-4" aria-hidden="true" />
                  </NuxtLink>
                </td>
                <td class="px-3 py-4 text-sm text-gray-500 whitespace-nowrap">
                  <NuxtLink to="#" class="inline-flex items-center text-red-600 hover:text-red-700">
                    <TrashIcon class="w-4 h-4" aria-hidden="true" />
                  </NuxtLink>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import {PlusIcon, TrashIcon, PencilIcon, EyeIcon} from "@heroicons/vue/solid/index";

const { data: posts } = await useFetch('https://jsonplaceholder.typicode.com/todos')

</script>