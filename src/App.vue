<template>
  <div class="app">
    <p>{{ jobs[0].location }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs, ref } from 'vue';
import Job from './types/Job'


export default defineComponent({
  name: 'App',
  components: {
    
  },
  setup() {
   
   const jobs = ref<Job[]>([
    { title: 'Farm Worker', location: 'Lon Lon Ranch', salary: 30000, id: '1' },
    { title: 'Quarryman', location: 'Death Mountain', salary: 40000, id: '2' },
    { title: 'Flute Player', location: 'The Lost Woods', salary: 35000, id: '3' },
    { title: 'Fisher Man', location: 'Lake Hylia', salary: 21000, id: '4' },
    { title: 'Prison Guard', location: 'Gerudo Valley', salary: 32000, id: '5' },
   ])

   return { jobs }
  },
  
});
</script>

<style>

</style>
