<template>
  <div id="app">
    
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
    // const name = ref('Link')
    // name.value = 'daniil'
    // const age = ref<number | string>(25)
    // age.value = 30

    // return {name, age}
  },
});
</script>

<style>

</style>
