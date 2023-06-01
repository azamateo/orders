import { text } from 'body-parser';

<template>
  <div class="about">
    <h1>Список покупок</h1>
    <h2>{{ name }}</h2>
    <form>
      <label>Имя</label>
      <input type="text" />
    </form>
  </div>
</template>
<script>
export default (await import("vue")).defineComponent({
  data() {
    return {
      name: "Test",
    };
  },
  methods: {
    changeName() {
      this.name = "value";
    },
  },
});
</script>
