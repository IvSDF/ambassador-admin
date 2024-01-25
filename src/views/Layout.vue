<template>
  <v-app>
    <Nav :user="user" />
    <div class="container-fluid">
      <div class="row">
        <Menu/>
        <main class="col-md-9 ms-sm-auto col-lg-10 px-md-4">
          <div class="table-responsive">
              <router-view></router-view>
          </div>
        </main>
      </div>
    </div>
  </v-app>
</template>

<script>
import Menu from "../components/Menu.vue";
import Nav from "../components/Nav.vue";
import axios from "axios";
import {User} from "@/models/user";
import Users from "@/views/Users.vue";

export default {
  name: "Layout",
  components: {Users, Menu, Nav},
  data(){
    return {
      user: new User(),
    }
  },

  async mounted() {
    try {
      const {data} = await axios.get('user');

      this.user = data;
    } catch (e) {
      await this.$router.push('/login')
    }
  }
}
</script>

<style scoped>

</style>