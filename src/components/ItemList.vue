<template>
    <div class="item-list">
      <h1 class="list-title">Item List Prelim</h1>
      <div v-for="item in filteredItems" :key="item.id">
        <Item :item="item" @add-to-cart="handleAddToCart"/>
      </div>
    </div>
  </template>
  
  <script>
  import Item from './Item.vue';
  
  export default {
    components: {
      Item
    },
    data() {
      return {
        items: [
          { id: 1, name: 'Shabu', price: 500, visible: true },
          { id: 2, name: 'Marijuana', price: 300, visible: true },
          { id: 3, name: 'Cocaine', price: 1000, visible: true }
        ]
      };
    },
    computed: {
      filteredItems() {
        return this.items.filter(item => item.visible);
      }
    },
    methods: {
      handleAddToCart(item) {
        console.log(Item added to cart: ${item.name}, Price: ${item.price});
      }
    }
  }
  </script>
  
  <style scoped>
  .item-list {
    font-family: 'Poppins', sans-serif;
    padding: 24px;
    width: 100%;
    background-color: #f8f9fa;
    border-radius: 8px;
  }
  
  .list-title {
    font-weight: 600;
    font-size: 2em;
    margin-bottom: 24px;
    color: #343a40;
  }
  </style>