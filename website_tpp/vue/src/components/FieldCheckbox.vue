<template>
  <input 
    type="checkbox"
    v-model="localValue"
    :disabled="disabled"
  >
</template>

<script>
  export default {
    data() {
      return {
        localValue: this.value,
      }
    },
    props: {
      value: { type: Boolean },
      disabled: { type: Boolean },
    },
    computed: {
    },
    watch: {
      value(newVal) {
        this.localValue = newVal;
      },
      localValue(newVal) {
        this.$emit('input',newVal);
      },
    },
  }
</script>
