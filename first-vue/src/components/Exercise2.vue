<script setup>
// this doesn't need "setup"
// export default {
//   data() {
//     return {
//       title: "my second component !",
//       isUppercase: false,
//     }
//   }
//}

// to use this "setup" is required in the script
const title = 'my first component!';
const isUppercase = true;
</script>

<template>
  <div>
    <h1>{{ isUppercase ? title.toUpperCase() : title }}</h1>
  </div>
</template>
