<script>
export default {
  data(){
    return{
      name: 'John Doe',
      status: 'active',
      tasks: ['task 1', 'task 2', 'task 3'],
      link: 'https://google.com'
    };
  },
  methods:{
    toggleStatus(){
      if (this.status === 'active') {
        this.status = 'pending'
      }else if(this.status === 'pending'){
        this.status = 'inactive'
      }else {
        this.status = 'active'
      }
    }
  }
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status == 'active'">User is Active</p>
  <p v-else-if="status == 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Task:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <!-- <a v-bind:href="link">click for Google</a> -->
  <a :href="link">click for Google</a>
  <br/>
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button v-on:click="toggleStatus">Change Status</button>
</template>

<style scoped>

</style>