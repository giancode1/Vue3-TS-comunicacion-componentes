<script setup lang="ts">
import { ref } from 'vue'

// defineProps<{ msg: string }>()

const count = ref(0)
const Sizes = ['xs', 's', 'm', 'l', 'xl', 'xxl']

//Javascript
// defineProps({
//   msg: String,
//   selectedSize: { type: String, required: true }
// })

// const emits = defineEmits([
//   // 'size-changed': String 
//   'onChangeSize'
// ])


//Typescript
// const props = defineProps({
//   msg: { type: String },
//   selectedSize: { type: String, required: true }
// })

//o
const props = defineProps<{
  msg: string,
  selectedSize: string
}>()

const emits = defineEmits<{
  (event: 'onChangeSize', size: string): void
}>()

</script>

<template>
  <h1>{{ msg }}</h1>
  <!-- <h3>selectedSize: {{ selectedSize }}</h3> -->
  <div>
    <button type="button" @click="count++">count is: {{ count }}</button>
  </div>

  <button
    v-for="size in Sizes"
    :class="{ 'active': selectedSize === size }"
    @click="emits('onChangeSize', size)"
  >{{ size }}</button>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
