<template>
  <v-app>
     <!--<v-main>
      <router-view />
    </v-main>-->
    <v-layout class="rounded rounded-md">
      <v-app-bar title="Application bar"></v-app-bar>
  
      <v-navigation-drawer>
        <v-list>
 
          <v-list-item link title="HOME" to="/"></v-list-item>
          <v-list-item link title="LINK" to="/memo"></v-list-item>
            
        </v-list>
      </v-navigation-drawer>
  
      <v-main class="d-flex align-center justify-center" style="min-height: 300px;">
        <router-view />
      </v-main>
    </v-layout>
    <AppFooter />
  </v-app>
</template>

<script lang="ts" setup>
  //
</script>
