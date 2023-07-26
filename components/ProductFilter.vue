<template>
    <div class="flex items-center">
      <div class="mr-4">
        <ul class="flex space-x-4">
          <li class="inline-block px-4 py-2 text-gray-500 border-b-2 border-transparent hover:bg-blue-500 hover:text-white cursor-pointer" :class="{ 'border-blue-500': activeTab === 0 }" @click="activeTab = 0">
            <a>All</a>
          </li>
          <li v-for="(category, index) in categories" :key="index" class="inline-block px-4 py-2 text-gray-500 border-b-2 border-transparent hover:bg-blue-500 hover:text-white cursor-pointer" :class="{ 'border-blue-500': activeTab === index + 1 }" @click="activeTab = index + 1">
            <a>{{ category }}</a>
          </li>
        </ul>
      </div>
      <div class="flex-1 mr-4">
        <div class="flex items-center border border-gray-300 rounded-md">
          <input type="text" class="w-full px-4 py-2 outline-none" placeholder="Search...">
          <button class="px-4 text-blue-500 focus:outline-none" @click="search"><i class="fas fa-search"></i></button>
        </div>
      </div>
      <div>
        <button class="px-4 py-2 text-white bg-blue-500 hover:bg-blue-700 rounded-md" @click="viewCart">
          Cart
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  let activeTab = ref(0); // Set activeTab to 0 for "All" category
  let categories = ref([]);
  
  const fetchCategories = async () => {
    try {
      const response = await fetch('https://fakestoreapi.com/products/categories');
      const data = await response.json();
      categories.value = data;
    } catch (error) {
      console.error('Failed to fetch categories.', error);
    }
  };
  
  onMounted(fetchCategories);
  
  const search = () => {
    // Search functionality
  };
  
  const viewCart = () => {
    // View cart functionality
  };
  </script>
  
  <style>
  /* CSS styles... */
  </style>
  
   <!-- <template>
    <div class="flex items-center">
      <div class="mr-4">
        <ul class="flex space-x-4">
          <li v-for="(category, index) in categories" :key="index" class="inline-block px-4 py-2 text-gray-500 border-b-2 border-transparent hover:bg-blue-500 hover:text-white cursor-pointer" :class="{ 'border-blue-500': activeTab === index + 1 }" @click="activeTab = index + 1">
            <a>{{ category }}</a>
          </li>
        </ul>
      </div>
      <div class="flex-1 mr-4">
        <div class="flex items-center border border-gray-300 rounded-md">
          <input type="text" class="w-full px-4 py-2 outline-none" placeholder="Search...">
          <button class="px-4 text-blue-500 focus:outline-none" @click="search"><i class="fas fa-search"></i></button>
        </div>
      </div>
      <div>
        <button class="px-4 py-2 text-white bg-blue-500 hover:bg-blue-700 rounded-md" @click="viewCart">
          Cart
        </button>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  
  let activeTab = ref(1);
  let categories = ref([]);
  
  const fetchCategories = async () => {
    try {
      const response = await fetch('https://fakestoreapi.com/products/categories');
      const data = await response.json();
      categories.value = data;
    } catch (error) {
      console.error('Failed to fetch categories.', error);
    }
  };
  
  onMounted(fetchCategories);
  
  const search = () => {
    // Search functionality
  };
  
  const viewCart = () => {
    // View cart functionality
  };
  </script>
  
  <style>
  /* CSS styles... */
  </style>
   -->