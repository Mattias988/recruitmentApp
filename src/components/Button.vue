<template>
  <button :class="class" type="button">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: {
      type: String,
      required: true
    },
    class: {
      type: String,
      default: ''
    }
  }
}
</script>
