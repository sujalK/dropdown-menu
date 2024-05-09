<template>
  <component
      :is="tag"
      class="dropdown-trigger"
  >
    <slot name="button-content"></slot>
  </component>
</template>
<script>
export default {
  props: {
    tag: {
      type: String,
      default: 'button',
      validator(value) {
        return ['button', 'a'].includes(value);
      }
    }
  }
}
</script>