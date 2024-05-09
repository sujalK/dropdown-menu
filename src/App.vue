<template>
  <Dropdown>
    <template v-slot:trigger-button="{ toggle }">
      <DropdownTrigger tag="button" @click="toggle">
        <template v-slot:button-content>
          <span>Pick One</span>
          <span class="lnr lnr-chevron-down"></span>
        </template>
      </DropdownTrigger>
    </template>
    <template v-slot:menu-content="{ toggle }">
      <DropdownItem @click.prevent="toggle">Web Development</DropdownItem>
      <DropdownItem @click.prevent="toggle">Mobile Development</DropdownItem>
      <DropdownItem @click.prevent="toggle">Database Design</DropdownItem>
      <DropdownItem @click.prevent="toggle">Data Science</DropdownItem>
    </template>
  </Dropdown>
</template>
<script>
import Dropdown from './components/Dropdown/Dropdown.vue';
import DropdownTrigger from './components/Dropdown/DropdownTrigger.vue';
import DropdownItem from './components/Dropdown/DropdownItem.vue';

export default {
  components: {
    Dropdown,
    DropdownTrigger,
    DropdownItem,
  },
}
</script>
<style>

</style>
