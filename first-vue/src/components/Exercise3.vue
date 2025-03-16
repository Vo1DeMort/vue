<script setup>
const text = 'directive text';
const html = 'stylise </br>html in <br/><b>your data</b>'
const link = {
  title: 'go to google',
  url: 'https://google.com',
  tabindex: 1,
  target: '_blank',
}
</script>

<template>
  <div>
    <h1 v-if="false" v-once v-text="text"></h1>
    <h2 v-html="html" v-show="false" />
    <a :href="link.url" :target="link.target" :tabindex="link.tabindex">
      {{ link.title }}
    </a>
  </div>
</template>
