<template>
  <div class="container">
    <h1>Список покупок</h1>
    <div v-if="shoppingList.length === 0">
      <p>Список покупок пуст.</p>
      <input v-model="newItem" placeholder="Введите покупку" />
      <button @click="addItem" :disabled="newItem === ''">Добавить</button>
    </div>
    <ul v-else>
      <li
        v-for="(item, index) in shoppingList"
        :key="index"
        @click="removeItem(index)"
      >
        {{ item }}
        <!-- <button @click="removeItem(index)">Удалить</button> -->
      </li>
      <input v-model="newItem" placeholder="Введите покупку" />
      <button @click="addItem" :disabled="newItem === ''">Добавить</button>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      shoppingList: ["Тв", "Приставка", "Саундбар"],
      newItem: "",
    };
  },
  methods: {
    addItem() {
      this.shoppingList.push(this.newItem);
      this.newItem = "";
    },
    removeItem(index) {
      this.shoppingList.splice(index, 1);
    },
  },
};
</script>

<style>
.container {
  margin-top: 2rem;
}
</style>
