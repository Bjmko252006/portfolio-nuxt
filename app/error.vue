
<template>
  <main class="min-h-screen bg-[#2a2a2a] text-white flex items-center justify-center px-6">
    <div class="text-center max-w-lg">
      <h1 class="text-8xl font-bold text-[#ff3333] mb-4">
        {{ error?.statusCode || 404 }}
      </h1>

      <h2 class="text-3xl font-semibold mb-4">
        Page Not Found
      </h2>

      <p class="text-gray-300 mb-8">
        Sorry, the page you are looking for does not exist
        or may have been moved.
      </p>

      <button
        class="btn bg-[#ff3333] border-none text-white hover:bg-red-700"
        @click="handleError"
      >
        Back to Home
      </button>
    </div>
  </main>
</template>

<script setup>
const props = defineProps({
  error: Object
})

const handleError = () => {
  clearError({ redirect: '/' })
}
</script>
