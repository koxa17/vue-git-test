<template>
  <div>
    <h1>Service List фцйвыфвфывфыв</h1>

    <v-select v-model="selected" :options="items" label="name" :clear-search-on-blur="clearFunction" :clear-search-on-select="false" >
      <template #selected-option="slotProps" >
        <slot name="selected-option" :slotProps="slotProps"></slot>
      </template>
      <template #selected-option-container="slotProps" >
        <slot name="selected-option-container" :slotProps="slotProps.option"></slot>
      </template>
    </v-select>

  </div>
</template>

<script setup>
import vSelect from "vue-select";
import { ref} from "vue";
/* eslint-disable */
const props = defineProps({
  items: {
    type: Array,
    required: true
  }
})
function dropdownShouldOpen(select) {
  console.log(select)
  return true
}
const selected = ref()

const clearFunction = ({ clearSearchOnSelect, multiple }) => {
  return clearSearchOnSelect && !multiple
}


</script>

<style scoped>

</style>