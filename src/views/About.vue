<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ name }},{{ getUserName }},{{ wallet }}
  </div>
  <button type="button" @click="updateName">click</button>
</template>

<script>
import { mapState, mapActions } from "pinia";
import userStore from "@/stores/user";

// compositioin API
// optionAPI
export default {
  computed: {
    // 1. store
    // 2. 要帶入的state,getters
    ...mapState(userStore, ["name", "getUserName", "wallet"]),
  },
  methods: {
    ...mapActions(userStore, ["updateName"]),
  },
};
</script>
