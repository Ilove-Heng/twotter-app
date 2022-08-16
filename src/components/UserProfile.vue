<template>
  <div class="user-profile">
    <div class="user-profile_user-panel">
      <h1 class="user-profile_username">@{{ user.username }}</h1>
      <div class="user-profile_admin-badge" v-if="user.isAdmin">Admin</div>
      <div class="user-profile_admin-badge" v-else>Not Admin</div>
      <div class="user-profile_follow-count">
        <strong>Followers:</strong> {{ followers }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserProfile",
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "_Seakheng",
        firstName: "Nang",
        lastName: "Seakheng",
        email: "seakheng@gmail.com",
        isAdmin: false,
      },
    };
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
};
</script>

<style>
.user-profile {
  display: grid;
  grid-template-columns: 1fr 3fr;
  width: 100%;
  padding: 50px 5%;
}
.user-profile_user-panel {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin-right: 50px;
  padding: 20px;
  gap: 10px;
  background-color: white;
  border: 1px solid #121212;
}
.user-profile_admin-badge {
  background: red;
  color: white;
  border-radius: 5px;
  padding: 0 10px;
  margin-right: auto;
}
h1 {
  margin: 0;
}
</style>