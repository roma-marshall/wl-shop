<template>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl px-4 py-0 sm:px-6 sm:py-0 lg:max-w-7xl lg:px-8">
      <h2 class="sr-only">Products</h2>
      <div
          aria-view="grid"
          class="grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-3 xl:gap-x-8"
          :class="`${cssGridCols}`"
      >
        <a @click="$router.push('/cart')" v-for="product in filteredProducts" :key="product.id" :href="product.href">
          <div class="shadow hover:saturate-150 hover:scale-105 active:scale-90 duration-500 aspect-h-1 aspect-w-1 w-full overflow-hidden rounded-lg bg-gray-200 xl:aspect-h-8 xl:aspect-w-7">
            <img :src="product.imageSrc" :alt="product.imageAlt" class="h-full w-full object-cover object-center group-hover:opacity-75" />
          </div>
          <h3 class="mt-4 text-sm text-gray-700">{{ product.name }}</h3>
          <p class="mt-1 text-lg font-medium text-gray-900">{{ product.price }}</p>
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  filteredProducts: {
    type: Array,
    default: [],
    required: true,
  },
  cssGridCols: {
    type: String,
  }
})
</script>