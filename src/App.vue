<script setup lang="ts">
import AddressForm from '@/components/AddressForm.vue'
import { ref } from 'vue'
import type { AddressFormData } from '@/types/AddressFormData'

const addressData = ref<AddressFormData>({
  postcode: '',
  houseNumber: 0,
  eddition: '',
  street: '',
  place: ''
})

const fetchData = ref(null)

const fetchAddressData = () => {
  fetch('http://localhost:3001/address')
    .then((response) => {
      if (!response.ok) {
        throw new Error('Network response was not ok')
      }
      return response.json()
    })
    .then((data) => {
      fetchData.value = data
      console.log(fetchData.value)
    })
    .catch((error) => {
      console.error('Fetch error:', error)
    })
}

fetchAddressData()
</script>

<template>
  <AddressForm v-model="addressData" />

  {{ addressData.postcode }}
  {{ addressData.houseNumber }}
  {{ addressData.street }}
  {{ addressData.place }}
</template>
