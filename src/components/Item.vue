<template>
  <div class="item-list">
    <h1 class="list-title">Item List</h1>
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
        { id: 1, name: 'Item 1', price: 100, visible: true },
        { id: 2, name: 'Item 2', price: 200, visible: false },
        { id: 3, name: 'Item 3', price: 300, visible: true }
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
      console.log(`Item added to cart: ${item.name}, Price: ${item.price}`);
    }
  }
}
</script>

<style scoped>
.item-list {
  padding: 24px;
  background-color: #f8f9fa;
  border-radius: 8px;
}

.list-title {
  font-size: 2em;
  margin-bottom: 24px;
  color: #343a40;
}
</style>