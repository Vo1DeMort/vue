<script>
import ListItem from './ListItem.vue'
</script>

<template>
  <ul>
    <ListItem :is-checked="item.checked" @click.prevent="updateItem(item)"> {{ item.title }}</ListItem>
  </ul>
</template>
