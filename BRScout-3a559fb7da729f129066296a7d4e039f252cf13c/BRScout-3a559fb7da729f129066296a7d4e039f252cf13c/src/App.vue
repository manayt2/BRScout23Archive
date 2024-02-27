<template>
  <ErrorList :errors="errors" />
  <RouterView />
</template>

<script setup lang="ts">
import ErrorList from "@/components/ErrorList.vue";
import { onErrorCaptured } from "vue";

const errors = $ref(new Array<string>());

// Set handler to capture errors and push them to an array
onErrorCaptured(e => {
  errors.push(`${e.name}: ${e.message}`);
  return false;
});
</script>

<style>
:root {
  --text-color: #ddd;
  --bg-color: #000000;
  --button-color: #3e3e3e;
  --input-color: #1c1c1c;
}

* {
  color: var(--text-color);
  box-sizing: border-box;
}

@font-face {
  font-family: MartelSans;
  src: url("/fonts/Martel_Sans/MartelSans-Regular.ttf") format("truetype");
  font-weight: normal;
}

@font-face {
  font-family: MartelSans;
  src: url("/fonts/Martel_Sans/MartelSans-Black.ttf") format("truetype");
  font-weight: bold;
}

img {
  display: block;
  user-select: none;
}

body {
  font-family: MartelSans, Arial, Helvetica, sans-serif;
  background-color: var(--bg-color);
  margin: 0;
  font-weight: normal;
}

h1 {
  font-weight: bold;
}

a {
  text-decoration:none;
}

ul {
    list-style-type: none;
}

button {
  background-color: var(--button-color);
  user-select: none;
  cursor: pointer;
  font-family: 'MartelSans';
  border-radius: 5px;
  background-color: #91d826;
  color: #020202;
  font-weight: bold;
}

input, select, textarea {
  background-color: var(--input-color);
}

button, input, select, textarea {
  font-size: 100%;
  border: none;
}

table {
  border-collapse: collapse;
}

td, th {
  border: 1px solid var(--text-color);
  padding: 2px;
}

</style>
