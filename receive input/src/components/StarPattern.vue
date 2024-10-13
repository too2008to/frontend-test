<script setup>
import { ref } from 'vue'

const inputNumber = ref(0)
const pattern = ref('')

const generatePattern = (event) => {
  event.preventDefault()  
  let result = ''
  const num = inputNumber.value

  for (let i = 1; i <= num; i++) {
    result += '*'.repeat(i) + '\n'
  }

  for (let i = num - 1; i >= 1; i--) {
    result += '*'.repeat(i) + '\n'
  }

  pattern.value = result
}
</script>

<template>
  <div class="flex justify-center items-center h-screen bg-base-200">
    <div class="card shadow-xl p-8 bg-white space-y-6">
      <form @submit="generatePattern" class="flex items-center space-x-4">
        <label class="label font-bold text-lg text-primary">
          Input:
        </label>
        <input
          v-model.number="inputNumber"
          type="number"
          placeholder="Enter a number"
          class="input input-bordered input-primary w-full max-w-xs rounded-lg shadow-md text-lg px-4 py-2 
          focus:outline-none focus:ring-4 focus:ring-blue-300 transition-all duration-300 ease-in-out 
          hover:shadow-lg hover:ring-2 hover:ring-blue-400"
        />
        <button
          type="submit"
          class="btn btn-primary btn-lg px-6 py-3 rounded-full shadow-xl transition duration-300 ease-in-out 
          hover:bg-blue-700 hover:shadow-2xl hover:scale-110 focus:ring-4 focus:ring-blue-300 active:scale-95"
        >
          Submit
        </button>
      </form>

      <pre class="mt-4">{{ pattern }}</pre>
    </div>
  </div>
</template>

<style scoped>
input {
  width: 100px;
}
pre {
  font-size: 16px;
  line-height: 1.5;
}
</style>
