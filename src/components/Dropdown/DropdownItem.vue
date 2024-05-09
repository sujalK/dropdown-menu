<template>
  <li>
    <a href="#" v-bind="$attrs">
      <slot />
    </a>
  </li>
</template>
<script>
export default {
  inheritAttrs: false,
}
</script>