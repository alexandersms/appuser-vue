<template>
  <div class="user-details">
    Id : {{ usr.id }}, Name : <strong>{{ usr.name }}</strong
    >, <br />
    Email : <strong>{{ usr.email }}</strong> <br />
    <button @click="acceptInvitation">Accept. invit.</button>
  </div>
</template>

<script>
export default {
  name: "UserDetails",
  props: ["usr"],
  methods: {
    acceptInvitation() {
      this.$emit("accept");
    }
  }
};
</script>

<style>
.user-details {
  border: 2px solid gray;
  margin: 10px;
  padding: 15px;
  width: 250px;
  float: left;
}
</style>
