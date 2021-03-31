<template>
  <div class="twit-item">
    <div class="user-profile-twit">
      <div class="twit-item-user">@{{ username }}</div>
      <div class="twit-item-content">{{ twit.content }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TwitItem",
  props: {
    username: {
      type: String,
      required: true,
    },
    twit: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
.twit-item {
  padding: 20px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid #dfe3e8;
  box-sizing: border-box;
  cursor: pointer;
  transition: all 0.25s ease;
  margin-top: 8px;
  width: 250px;
  overflow: hidden;
}

.twit-item:hover {
  transform: scale(1.1, 1.1);
}

.twit-item-user {
  font-weight: 700;
}

.twit-item-content {
  margin-top: 8px;
  font-weight: 300;
}
</style>