<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <UserList :data="users" :user-welcome="userWhoWillCome"></UserList>
    <div v-for="user in userWhoWillCome" :key="user.id">
      {{ user.id }} - {{ user.username }}
    </div>
  </div>
</template>

<script>
import UserList from "./components/UserList.vue";
import axios from "axios";
export default {
  name: "app",
  components: {
    UserList
  },
  data() {
    return {
      title: "Liste Utilisateurs",
      userUrl: "https://jsonplaceholder.typicode.com/users",
      users: [],
      userWhoWillCome: []
    };
  },
  created() {
    axios.get(this.userUrl).then(response => {
      this.users = response.data;
    });
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #58595a;
  font-size: 11px;
}

h1 {
  font-size: 40px;
}

li {
  list-style: none;
}
</style>
