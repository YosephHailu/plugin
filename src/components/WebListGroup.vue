<template>
  <ul class="bg-white rounded-lg border border-gray-200 w-96 text-gray-900">
    <li
      class="even:bg-gray-200 px-6 py-2 border-b border-gray-200 w-full hover:bg-gray-300 hover:cursor-pointer"
      v-for="(item, index) in items"
      :key="index"
      @click="$emit('select', [item[value]])"
    >
      {{ item[label] }}
    </li>
  </ul>
</template>

<script lang="ts" setup>
import { reactive } from "@vue/reactivity";

const props = defineProps({
  items: {
    type: [],
  },
  label: {
    type: String,
    default: "label",
  },
  nth: {
    type: Number,
    default: 1,
  },
  value: {
    type: String,
    default: "value",
  },
});
</script>
