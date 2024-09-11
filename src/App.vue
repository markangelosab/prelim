<template>
  <div id="app" class="app-container">
    <ItemList/>
  </div>
</template>

<script>
import ItemList from './components/ItemList.vue';

export default {
  components: {
    ItemList
  }
}
</script>

<style>
#app {
  text-align: center;
  border-radius: 10px;
  background-color: pink;
  height: auto;
  width: 500px;
  padding: 20px 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.app-container {
  width: 100%;
  max-width: 900px;
  padding: 20px;
  background-color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}
</style>