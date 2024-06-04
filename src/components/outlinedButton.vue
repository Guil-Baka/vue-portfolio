<script setup lang="ts">
import { defineProps } from 'vue'
import { ref } from 'vue'

const props = defineProps<{
  disabled: boolean,
}>()

const active = ref(false)

//onmouseup
const handleMouseUp = () => {
  //check if the button is disabled
  if (props.disabled) {
    active.value = !active.value
  }
}

//onmousedown
const handleMouseDown = () => {
  //check if the button is disabled
  if (props.disabled) {
    active.value = !active.value
  }
}
</script>

<template>
  <button
    class="button"
    :disabled="props.disabled"
    @mouseup="handleMouseUp"
    @mousedown="handleMouseDown"
  >
    <slot></slot>
  </button>

</template>
<style scoped>
 
.button {
  padding: 0.5rem 1rem;
  border: 1px solid #C4FF82;
  border-radius: 15px;
  background: var(--color-background);
  color: var(--color-text);
  font-size: 1rem;
  cursor: pointer;
}

.button:disabled {
  background: #1c1c1c;
  cursor: not-allowed;
  border-color: #ff0000;
}

/* if the button is not disabled have the hover and active animations */
button:not(:disabled):hover {
  background: #C4FF82;
  color: black;
}

.button:not(:disabled):active {
  /*
   create a bigger outline when the button is clicked
   */
  box-shadow: 0 0 0 3px #C4FF82;
}


</style>