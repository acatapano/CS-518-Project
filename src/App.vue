<script setup lang="ts">
import Todos from './components/Todos.vue'

import { Authenticator } from "@aws-amplify/ui-vue";
import "@aws-amplify/ui-vue/styles.css";
</script>

<template>
  <main>  
    <authenticator>
      <!-- <template v-slot="{ signOut }"> -->       
      <template v-slot="{ user, signOut }">
        <h1>{{user?.signInDetails?.loginId}}'s Notes</h1>
        <Todos />
        <button @click="signOut">Sign Out</button>
      </template>
    </authenticator>
    <!-- <Todos /> -->
  </main>
</template>

