<template>
  <div class="user-profile">
    <div class="user-profile-user-panel">
      <h1 class="user-profile-username">@{{ user.username }}</h1>
      <div v-if="user.isAdmin" class="user-profile-admin-badge">Admin</div>
      <div class="user-profile-follower-count">
        <small>Followers : {{ followers }}</small>
      </div>
    </div>
    <div class="user-profile-twits-wrapper">
      <twit-item
        v-for="twit in user.twits"
        :key="twit.id"
        :username="user.username"
        :twit="twit"
      />
    </div>
  </div>
</template>

<script>
import TwitItem from "./TwitItem.vue";
export default {
  components: { TwitItem },
  name: "UserProfile",
  data() {
    // isinya deklarasi variabel
    return {
      followers: 0,
      user: {
        id: 1,
        username: "_joywisnu",
        firstName: "joy",
        lastName: "wisnu",
        email: "joywisnu@mail.com",
        isAdmin: true,
        twits: [
          { id: 1, content: "anjay" },
          { id: 2, content: "skuy mabar" },
        ],
      },
    };
  },
  computed: {
    // isinya variabel di data yang udah diproses
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
  },
  methods: {
    // isinya subprogram
    followUser() {
      this.followers++;
    },
  },
  mounted() {
    // jalan pas komponen ini kebuat
    this.followUser();
  },
  watch: {
    // jalan pas ada variabel yang berubah
    followers(newFollowers, oldFollowers) {
      console.log(`${oldFollowers} - ${newFollowers}`);
      if (oldFollowers < newFollowers) {
        console.log(`${this.user.username} has gained a follower`);
      }
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
  margin-left: 8px;
}
.user-profile-user-panel {
  display: flex;
  flex-direction: column;
  margin-right: 50px;
  padding: 20px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid #dfe3e8;
}
h1 {
  margin: 0%;
}
.user-profile-admin-badge {
  background-color: indianred;
  color: white;
  border-radius: 10px;
  margin-right: auto;
  padding: 0px 10px;
  margin-top: 6px;
  margin-bottom: 4px;
  font-weight: 700;
}

.user-profile-username {
  font-weight: 400;
}

.user-profile-follower-count {
  font-weight: 300;
}
</style>