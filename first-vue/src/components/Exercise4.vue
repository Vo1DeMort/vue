<script setup>
import { ref } from "vue"
var name = ref('');
var language = ref('');
</script>
<!-- <script> -->
<!-- export default { -->
<!--   data() { -->
<!--     return { -->
<!--       name: '', -->
<!--       language: '', -->
<!--     } -->
<!--   } -->
<!-- } -->
<!-- </script> -->

<template>
  <div class="form">
    <label for="">
      Name
      <input type="text" v-model="name">
    </label>
  </div>
  <br>
  <div>
    <label for="">
      Preferred JavaScript style</label>
    <select name="language" v-model="language" id="">
      <option value="JavaScript">JavaScript</option>
      <option value="TypeScript">TypeScript</option>
      <option value="CoffeeScript">CoffeeScript</option>
      <option value="Dart">Dart</option>
    </select>
  </div>
  <ul class="overview">
    <li><strong>Overview</strong></li>
    <li>Name: {{ name }}</li>
    <li>Preference: {{ language }}</li>
  </ul>
</template>

<style>
.form {
  display: flex;
  justify-content: space-evenly;
  max-width: 800px;
  padding: 40px 20px;
  margin: 0 auto;
  background: #ececec;
}

.overview {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  max-width: 300px;
  margin: 40px auto;
  padding: 40px 20px;
  border-radius: 10px;
  border: 1px solid #ececec;
}

.overview>li {
  list-style: none;
}

.overview>li+li {
  margin-top: 20px;
}
</style>
