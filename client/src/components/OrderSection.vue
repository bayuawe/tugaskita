<template>
  <section class="py-12 px-4 sm:px-6 lg:px-8" id="order">

    <div class="max-w-4xl mx-auto px-4 py-5 sm:p-6 bg-white shadow-lg border border-[#1f1641] rounded-xl">
      <h2 class="text-2xl font-bold mb-4 text-gray-800">Place Your Order</h2>
      <form @submit.prevent="submitOrder" class="space-y-4">
        <div>
          <label for="subject" class="block text-sm font-medium text-gray-700">Subject</label>
          <input id="subject" v-model="order.subject" type="text" required
            class="mt-1 block w-full rounded-md bg-gray-200 border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500 focus:ring-opacity-75">
        </div>



        <div>
          <label for=" description" class="block text-sm font-medium text-gray-700">Description</label>
          <textarea id="description" v-model="order.description" rows="3" required
            class="mt-1 block w-full rounded-md bg-gray-200 border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500 focus:ring-opacity-75"></textarea>
        </div>

        <div>
          <label for="expertize" class="block text-sm font-medium text-gray-700">Expertise</label>
          <select id="expertize" v-model="order.expertize_id" required class="mt-1 block w-full rounded-md bg-gray-200
            border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500
            focus:ring-opacity-75">
            <option value="">Select an expertise</option>
            <option v-for=" expertize in expertizes" :key="expertize.id" :value="expertize.id">
              {{ expertize.name }}
            </option>
          </select>
        </div>

        <div>
          <label for="deadline" class="block text-sm font-medium text-gray-700">Deadline</label>
          <input id="deadline" v-model="order.deadline" type="datetime-local" required class="mt-1 block w-full rounded-md bg-gray-200
            border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500
            focus:ring-opacity-75" />
        </div>

        <div>
          <label for="attachments" class="block text-sm font-medium text-gray-700">Attachments</label>
          <input id="attachments" type="file" @change="handleFileUpload"
            class="mt-1 block w-full text-sm text-gray-500 file:mr-4 file:py-2 file:px-4 file:rounded-full file:border-0 file:text-sm file:font-semibold file:bg-indigo-50 file:text-indigo-700 hover:file:bg-indigo-100" />
        </div>

        <div>
          <label for="client_name" class="block text-sm font-medium text-gray-700">Your Name</label>
          <input id="client_name" v-model="order.client_name" type="text" required class="mt-1 block w-full rounded-md bg-gray-200
            border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500
            focus:ring-opacity-75" />
        </div>

        <div>
          <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
          <input id="email" v-model="order.email" type="email" required class="mt-1 block w-full rounded-md bg-gray-200
            border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500
            focus:ring-opacity-75" />
        </div>

        <div>
          <label for="phone" class="block text-sm font-medium text-gray-700">Phone</label>
          <input id="phone" v-model="order.phone" type="tel" required class="mt-1 block w-full rounded-md bg-gray-200
            border-gray-500 text-gray-900 shadow-sm focus:border-indigo-400 focus:ring focus:ring-indigo-500
            focus:ring-opacity-75" />
        </div>

        <div>
          <button type="submit"
            class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-medium text-gray-700 bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
            Submit Order
          </button>
        </div>
      </form>

      <div v-if="errorMessage" class="mt-4 text-red-600">
        {{ errorMessage }}
      </div>
    </div>

  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const expertizes = ref([
  { id: 1, name: 'Computer Science' },
  { id: 2, name: 'Engineering' },
  { id: 3, name: 'Business' },
  // Add more expertizes as needed
])

const order = reactive({
  subject: '',
  description: '',
  expertize_id: '',
  deadline: '',
  attachments: null,
  client_name: '',
  email: '',
  phone: ''
})

const errorMessage = ref('')

const handleFileUpload = (event) => {
  order.attachments = event.target.files[0]
}

const submitOrder = async () => {
  errorMessage.value = ''

  // Basic form validation
  if (!order.subject || !order.description || !order.expertize_id || !order.deadline ||
    !order.client_name || !order.email || !order.phone) {
    errorMessage.value = 'Please fill in all required fields.'
    return
  }

  // Create FormData object to send file
  const formData = new FormData()
  for (const key in order) {
    formData.append(key, order[key])
  }

  try {
    // Replace with your actual API endpoint
    const response = await fetch('/api/orders', {
      method: 'POST',
      body: formData
    })

    if (!response.ok) {
      throw new Error('Failed to submit order')
    }

    // Handle successful submission
    alert('Order submitted successfully!')
    // Reset form
    Object.keys(order).forEach(key => order[key] = '')
    order.expertize_id = ''
  } catch (error) {
    console.error('Error submitting order:', error)
    errorMessage.value = 'An error occurred while submitting your order. Please try again.'
  }
}
</script>
