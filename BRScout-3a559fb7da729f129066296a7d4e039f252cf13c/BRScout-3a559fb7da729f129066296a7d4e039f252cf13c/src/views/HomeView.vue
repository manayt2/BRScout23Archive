<template>
  <div id="home-container">
    <Suspense>
      <template #default>
        <HomePage />
      </template>
      <template #fallback>Loading...</template>
    </Suspense>
  </div>
</template>

<script setup lang="ts">
import HomePage from "@/components/HomePage.vue";
</script>

<style>
#home-container {
  display: grid;
  justify-content: center;
  height: 100vh;
  background-image: url("../../public/assets/matrix.gif");
  background-repeat: repeat;
}

h2 {
  margin: 0;
}
</style>
