<template>
    <!-- <h1>Batch 48</h1>

    {{ products }} -->

<div class="min-h-screen bg-gray-100">
    <!-- <ProductFilter/> -->
  <div class="container mx-auto py-8">
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
      <!-- <div v-for="product in products" :key="'product' + product.id" class="bg-white shadow-lg rounded-lg overflow-hidden">
        <div class="p-6">
          <img :src="product.image" alt="" class="w-full max-h-[200px] object-contain mb-4">
          <h2 class="text-lg text-gray-800 font-semibold mb-2 overflow-ellipsis overflow-hidden h-16">{{ product.title }}</h2>
          <p class="text-gray-600 text-sm mb-4 overflow-ellipsis overflow-hidden h-16">{{ product.description}}</p>
          <div class="flex items-center mb-2">
            <div class="mr-2 bg-yellow-400 rounded-lg p-2">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-white" viewBox="0 0 20 20" fill="currentColor">
                <path fill-rule="evenodd" d="M10 1a1 1 0 00-.795.394L6 5.586l-3.205.47a1 1 0 00-.55 1.705l2.32 2.26-.547 3.192a1 1 0 001.45 1.055L10 12.713l2.433 1.277a1 1 0 001.45-1.056l-.547-3.191 2.32-2.26a1 1 0 00-.55-1.704L14 5.587l-3.205-.47A1 1 0 0010 1zm4.222 6.148a.5.5 0 01.278.848l-2.082 2.027.49 2.86a.5.5 0 01-.724.528L10 12.728l-2.175 1.146a.5.5 0 01-.724-.527l.492-2.862-2.082-2.027a.5.5 0 01.278-.848l2.858-.416 1.276-2.593a.5.5 0 01.899 0l1.276 2.593 2.858.416z" clip-rule="evenodd" />
              </svg>
            </div>
            <span class="text-gray-700 text-sm">{{ product.rating.rate }}</span>
            <span class="text-gray-700 text-sm ml-1">{{ product.rating.count }}</span>
          </div>
          <div class="flex items-center">
            <span class="text-gray-700 font-semibold">{{ product.price }}</span>
            <button class="ml-auto bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
              Add to Cart
            </button>
          </div>
        </div>
      </div> -->
      <ProductCard
      v-for="product in products" 
      :key="'product' + product.id"
      :product="product"
      />
    </div>
  </div>
</div>


</template> 

<script setup>

const products = await $fetch('https://fakestoreapi.com/products/')

</script>