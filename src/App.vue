<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="site logo">
        <h1>Hyrule Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>
    <JobList 
      :jobs="jobs"
      :order="order"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import JobList from './components/JobList.vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'


export default defineComponent({
  name: 'App',
  components: {
    JobList
  },
  setup() {
   
   const jobs = ref<Job[]>([
    { title: 'Farm Worker', location: 'Lon Lon Ranch', salary: 30000, id: '1' },
    { title: 'Quarryman', location: 'Death Mountain', salary: 40000, id: '2' },
    { title: 'Flute Player', location: 'The Lost Woods', salary: 35000, id: '3' },
    { title: 'Fisher Man', location: 'Lake Hylia', salary: 21000, id: '4' },
    { title: 'Prison Guard', location: 'Gerudo Valley', salary: 32000, id: '5' },
   ])
   const order=ref<OrderTerm>('title')

   const handleClick = (term: OrderTerm) => {
    order.value = term
   }
   return { jobs, handleClick, order }
  },
  
});
</script>

<style>
  header {
    text-align: center;
  }

  header .order {
    margin-top: 20px;
}

  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }

  header .title {
    display: flex;
    justify-content: center;
  }

  header img {
    width: 60px;
    margin-right: 20px;
  }

  header h1 {
    font-size: 3em;
  }
</style>
