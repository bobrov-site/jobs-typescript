<template>
  <div id="app">
    <JobsList :jobs="jobs"/>
  </div>
</template>

<script lang="ts">
// должен быть импорт для reactive и toRefs ⬇️
import { defineComponent, ref } from 'vue';
import JobsList from './components/JobsList.vue';
import Job from './types/Job'

export default defineComponent({
  name: 'App',
  components: {JobsList},
  setup() {
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
