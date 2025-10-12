<template>
  <div class="input__field">
    <div class="input__field-inner">
      <label v-if="label" :for="name">{{ label }}</label>
      <input @input="$emit('update:modelValue', $event.target.value)"
             :name="name" :type="type" :placeholder="placeholder">
    </div>
    <p v-if="error" class="input__field-error">{{ error }}</p>
  </div>
</template>

<script setup>
const props = defineProps({
  modelValue: String,
  name: String,
  type: { type: String, default: 'text' },
  label: String,
  error: String,
  placeholder: String
})
const emit = defineEmits(['update:modelValue'])

</script>

<style lang="scss" scoped>

</style>