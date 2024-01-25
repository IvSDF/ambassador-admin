<template>
     <table class="table table-striped table-sm">
    <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Name</th>
      <th scope="col">Email</th>
      <th scope="col">Actions</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="user in users" :key="user.id">
      <td>{{ user.id }}</td>
      <td>{{ user.first_name }} {{ user.last_name }}</td>
      <td>{{ user.email }}</td>
      <td></td>
    </tr>
    </tbody>
  </table>
</template>

<script>
import axios from "axios";

export default {
  name: "Users",
  data() {
    return {
      users: [],
    }
  },
  async mounted() {
    const {data} = await axios.get('ambassadors');

    this.users = data;

  }
}
</script>