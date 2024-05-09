<template>
  <div class="dropdown" v-click-out-side="closeMenu">
    <slot name="trigger-button" :toggle="toggleMenu"></slot>
    <ul class="dropdown-menu" v-show="isOn">
      <slot name="menu-content" :toggle="toggleMenu"></slot>
    </ul>
  </div>
</template>
<script>
import clickOutSide from "@mahdikhashan/vue3-click-outside";

export default {
  directives: {
    clickOutSide
  },
  data () {
    return {
      isOn: false
    }
  },
  methods: {
    toggleMenu() {
      this.isOn = ! this.isOn;
    },
    closeMenu() {
      this.isOn = false;
    }
  }
}
</script>
<style>
.dropdown {
  display: inline-block !important;
  position: relative;
}

.dropdown-trigger {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  width: 217px;
  border: none;
  background: #999;
  border-radius: 2px;
  padding: .65rem;
  color: #fff;
  font-size: 1rem;
  cursor: pointer;
  transition: .2s background;
  outline: none;
}

.dropdown-trigger > * {
  max-width: 100%;
}

.dropdown-trigger:hover {
  background: #888;
}

.dropdown-menu {
  position: absolute;
  left: 0px;
  top: 32px;
  list-style-type: none;
  width: 100%;
  max-width: 215px;
  border: 1px solid #ebebeb;
  border-radius: 2px;
  padding-left: 0;
}

.dropdown-menu > li {
  width: 100%;
  cursor: pointer;
  border-bottom: 1px solid #ebebeb !important;
}

.dropdown-menu > li:hover {
  background: #ebebeb;
}

.dropdown-menu > li:last-child {
  border-bottom: none !important;
}

.dropdown-menu > li a {
  display: block;
  text-align: center;
  text-decoration: none;
  color: #000;
  padding: .75rem 0;
}
</style>