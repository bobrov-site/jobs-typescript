<template>
  <div id="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('zelda' )">change name</button>
    <button @click="changeAge('13' )">change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},
  data() {
    return {
      name: 'Link',
      //можно добавить типы
      age: 25 as number | string
    }
  },
  methods: {
    changeName(name: string) {
      this.name = name
    },
    changeAge(age: number | string) {
      this.age = age
    }
  }
});
</script>

<style>

</style>
