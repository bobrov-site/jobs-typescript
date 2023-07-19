<template>
  <div id="app">
    <p>{{ name }}</p>
    <button @click="changeName('zelda' )">change name</button>
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
    }
  }
});
</script>

<style>

</style>
