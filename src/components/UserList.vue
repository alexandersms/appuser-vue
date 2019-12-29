<template>
  <div>
    <ul>
      <li v-for="user in data" :key="user.id">
        <UserDetails :usr="user" @accept="registerUser(user)"></UserDetails>
      </li>
    </ul>
  </div>
</template>

<script>
import UserDetails from "./UserDetails.vue"
export default {
  name: "UserList",
  components: {
    UserDetails
  },
  props: ["data", "userWelcome"],
  methods: {
    registerUser(user) {
      this.userWelcome.push(user); 
    }
  },
  data() {
    return {
      userWhoWillCome: []
    };
  }
};
</script>

<style></style>
