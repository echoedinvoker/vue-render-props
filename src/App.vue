<template>
  <div>
    <h1>Render Props Demo</h1>
    <div className="col-2">
      <TheList title="Products" :items="products">
        <template #default="{ isOpen, displayItems }">
          <ul className="list" v-if="isOpen">
            <ProductItem v-for="product in displayItems" :key="product.productName" :product="product" />
          </ul>
        </template>
      </TheList>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import TheList from './TheList.vue';
import { products as productsData } from './data';
import ProductItem from './ProductItem.vue';

const products = ref(productsData)
</script>
