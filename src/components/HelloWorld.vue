<script setup>
import { ref } from 'vue'
import { LuxInputButton, LuxIconApproved, LuxIconBase } from 'lux-design-system'


defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <lux-input-button variation="solid" size="small">Apply Changes</lux-input-button>
      <lux-dropdown-menu type="links" button-label="Select Options" :menu-items="[
      {name: 'Vegetable'},
      {name: 'Fruit', children: [
        {name: 'Apple'},
        {name: 'Pear'},
      ]},
    ]">
    </lux-dropdown-menu>
    My icon:
    <lux-icon-base width="12" height="12" icon-name="Approved">
      <lux-icon-approved></lux-icon-approved>
    </lux-icon-base>
  <h1>{{ msg }}</h1>
</template>
