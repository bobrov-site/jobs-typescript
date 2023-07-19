<template>
  <div id="app">
    <div class="btns">
      <button @click="handleClick('title')" class="btn">Order by title</button>
      <button @click="handleClick('salary')" class="btn">Order by salary</button>
      <button @click="handleClick('location')" class="btn">Order by location</button>
    </div>
    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
// должен быть импорт для reactive и toRefs ⬇️
import { defineComponent, ref } from 'vue';
import JobsList from './components/JobsList.vue';
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'

export default defineComponent({
  name: 'App',
  components: { JobsList },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'Moscow', salary: 3000, id: '1' },
      { title: 'fisher', location: 'Stavropol', salary: 4000, id: '2' },
      { title: 'developer', location: 'Krasnodar', salary: 5000, id: '3' },
      { title: 'ceo', location: 'Minsk', salary: 5000, id: '4' },
      { title: 'ui designer', location: 'Kuban', salary: 6000, id: '4' }
    ])

    const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term
    }

    return { jobs, handleClick, order }
  },
});
</script>

<style lang="css" scoped>
.btns {
  margin-left: 3rem;
}
.btn {
  display: inline-block;
  padding: 12px 24px;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  text-decoration: none;
  background-color: #4CAF50;
  color: #fff;
  border-radius: 4px;
  transition: background-color 0.3s ease;
  margin-right: 2rem;
}

.btn:hover {
  background-color: #45a049;
  cursor: pointer;
}
</style>
