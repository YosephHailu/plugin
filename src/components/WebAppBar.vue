<template>
  <nav
    class="flex items-center border-b shadow-lg justify-between flex-wrap bg-white p-6"
  >
    <div class="flex items-center flex-shrink-0 mr-6">
      <slot name="logo"></slot>
      <slot name="title">
        <span class="font-semibold text-xl mt-1 tracking-tight uppercase">{{
          title
        }}</span>
      </slot>
    </div>
    <div class="block lg:hidden">
      <button
        class="flex items-center px-3 py-2 border rounded border-teal-400 hover:text-white hover:border-white"
      >
        <svg
          class="fill-current h-3 w-3"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <title>Menu</title>
          <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
        </svg>
      </button>
    </div>

    <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
      <div class="text-sm lg:flex-grow">
        <a
          v-for="(item, index) in items"
          :key="index"
          href="#responsive-header"
          class="block mt-4 lg:inline-block lg:mt-0 hover:text-white mr-4"
        >
          {{ item["label"] }}
        </a>
      </div>

      <slot name="right-side"></slot>
    </div>
  </nav>
</template>

<script lang="ts" setup>
import type { PropType } from "@vue/runtime-core";


interface Item {
  label: string;
  link: string;
}

defineProps({
  title: {
    type: String,
  },
  items: {
    type: Array as PropType<Item[]>,
    default: () => [
      { label: "Docs", link: "#Docs" },
      { label: "Examples", link: "#Examples" },
      { label: "Blog", link: "#Blog" },
    ],
  },
});
</script>
