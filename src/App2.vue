<script>
export default {
  name:"App",
  data(){
    return{
      name:"John Doe",
      status: 'pending',
      tasks: ['Task One','Task Two','Task Three'],
      link: 'https://www.google.com.ng/'
    }
  },
  methods:{
    toggleStatus(){
      if(this.status ==="pending"){
        this.status = "active"
      }else if(this.status ==="active"){
        this.status = "inactive"
      }else{
        this.status = "pending"
      }
    }
  }
}
</script>
<template>
<h1>{{ name }}</h1>
<p v-if="status === 'active'">User is active</p>
<p v-else-if="status === 'pending'">User is pending</p>
<p v-else>User is inactive</p>
<h3>Tasks:</h3>
<ul>
  <li v-for="i in tasks" :key="i">{{ i }}</li>
</ul>
<!-- <a v-bind:href="link">Google</a> -->
<a :href="link">Google</a>
  <!-- <button v-on:click="toggleStatus" >Change Status</button> -->
  <button @click="toggleStatus" >Change Status</button>
</template>
<style>
a{
  display: block;
}
</style>
<!-- <script setup>
import { ref , onMounted} from 'vue';

    const name = ref("John Doe");
    const status = ref("pending");
    const tasks = ref(['Task One', 'Task Two', 'Task Three']);
    const link = 'https://www.google.com';
    const t = ref('');
    const toggleStatus = ()=>{
      if(status.value ==="pending"){
        status.value = "active";
      }else if(status.value ==="active"){
        status.value = "inactive";
      }else{
        status.value = "pending";
      }
    };
    const addTask = ()=>{
    if(t.value.trim() !== ''){
      tasks.value.push(t.value);
      t.value = '';
    }
    };
    const removeTask = (index)=>{
      // tasks.value.splice(index, 1);
      tasks.value.pop(tasks[index]);
    };
    onMounted(async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/todos');
        const data = await response.json();
        tasks.value = data.map((i) => i.title); 
      } catch(error) {
       console.log('Error fetching tasks');
      }
    });

</script>
<template>
<h1>{{ name }}</h1>
<p v-if="status === 'active'">User is active</p>
<p v-else-if="status === 'pending'">User is pending</p>
<p v-else>User is inactive</p>

<form @submit.prevent="addTask">
  <label for="t">Input your Task:</label>
  <input type="text" id="t" name="t" v-model="t">
  <input type="submit" id="t">
</form>
<h3>Tasks:</h3>
<ul>
  <li v-for="(i, index) in tasks" :key="i">
    <span>
      {{ i }}
    </span>
    <button @click="removeTask(index)">X</button>
  </li>
</ul>
 <a v-bind:href="link">Google</a> -->
<!-- <a :href="link">Google</a> -->
  <!-- <button v-on:click="toggleStatus" >Change Status</button>
  <button @click="toggleStatus" >Change Status</button>
</template>
<style scoped>
a{
  display: block;
}
</style> -->