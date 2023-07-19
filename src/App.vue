<template>
  <div id="app">
    <p>{{ jobs[0].location }}</p>
  </div>
</template>

<script lang="ts">
// должен быть импорт для reactive и toRefs ⬇️
import { defineComponent, ref } from 'vue';
import Job from './types/Job'

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

    const jobs = ref<Job[]>([
      {title: 'farm worker', location: 'Moscow', salary: 3000, id: '1'},
      {title: 'fisher', location: 'Stavropol', salary: 4000, id: '2'},
      {title: 'developer', location: 'Krasnodar', salary: 5000, id: '3'},
      {title: 'ceo', location: 'Minsk', salary: 5000, id: '4'},
      {title: 'ui designer', location: 'Kuban', salary: 6000, id: '4'}
    ])
    return {jobs}
  },
});
</script>

<style>

</style>
