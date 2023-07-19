<template>
  <div id="app">
    <p>{{ name }} - {{ age }}</p>
    <button @click="changeName('zelda' )">change name</button>
    <button @click="changeAge('13' )">change age</button>
  </div>
</template>

<script lang="ts">
// должен быть импорт для reactive и toRefs ⬇️
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    //использование через реактив

    // const state = reactive({
    //   name: 'Link',
    //   age: 25 as string | number
    // })
    // return {...toRefs(state)}

    //использование через рефы
    const name = ref('Link')
    name.value = 'daniil'
    const age = ref<number | string>(25)
    age.value = 30

    return {name, age}
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
