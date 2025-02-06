<template>
  <div>
    <button @click="toggleActive">Toggle Active State</button>
    <div :class="classObject">
      This div will change classes based on the active state.
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const isActive = ref(false)

const classObject = computed(() => ({
  'active-class': isActive.value,
  'inactive-class': !isActive.value
}))

const toggleActive = () => {
  isActive.value = !isActive.value
}
</script>

<style>
.active-class {
  background-color: green;
  color: white;
}

.inactive-class {
  background-color: gray;
  color: black;
}
</style>


