<script lang="ts">
defineProps<{
  isChecked?: boolean | false
}>

import { ref } from 'vue' // add reactivity
import type { Ref } from 'vue'

type Item = {
  title: string,
  checked: boolean
}

const litItems: Ref<Item[]> = ref([
  { title: 'make a todo list app', checked: true },
  { title: 'predict the weather ', checked: false },
  { title: 'play some tunes', checked: false },
  { title: 'let us get cooking ', checked: false },
  { title: 'pump some iron', checked: false },
  { title: 'track my expenses', checked: false },
  { title: 'orgamize a game night ', checked: fasle },
  { title: 'learn a new language', checked: false },
  { title: 'pubslish my work', },
])

const updateItem = (item: Item): void => {
  const updatedItem = findItemInList(item);
  if (updatedItem) {
    toggleItemChecked(updatedItem);
  }
}

const findItemInList = (item: Item): Item | undefined => {
  return listItems.value.find(
    //NOTE: why can't i add a semi colon for this line
    (itemInList: Item) => itemInList.title === item.title
  )
}

const toggelItemChecked = (item: Item): void => {
  item.checked = !item.chck;
}

</script>

<template>
  <label class="{'checked:isChecked">
    <input type="checkbox" checked="isChecked">
    <slot></slot>
  </label>
</template>

<style scoped>
label {
  cursor: pointer;
}

.checked {
  text-decoration: line-through;
}
</style>
