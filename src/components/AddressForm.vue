<script setup lang="ts">
import { resourceText } from '@/resourceText'
import type { AddressFormData } from '@/types/AddressFormData'

const addressData = defineModel<AddressFormData>({ required: true })

// console.log(addressData.value)
</script>

<template>
  <div class="isolate bg-white px-6 py-24 sm:py-32 lg:px-8">
    <div
      class="absolute inset-x-0 top-[-10rem] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[-20rem]"
      aria-hidden="true"
    ></div>
    <div class="mx-auto max-w-2xl text-center">
      <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">
        {{ resourceText.addressTitle }}
      </h2>
    </div>
    <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-3">
      <div>
        <label for="postcode" class="block text-sm font-semibold leading-6 text-gray-900">{{
          resourceText.addressPostcodeLabel
        }}</label>
        <div class="mt-2.5">
          <input
            type="text"
            name="postcode"
            id="postcode"
            v-model="addressData.postcode"
            :placeholder="resourceText.addressPostcodePlaceholder"
            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
          />
        </div>
      </div>
      <div>
        <label for="house-number" class="block text-sm font-semibold leading-6 text-gray-900">{{
          resourceText.addressHouseNumberLabel
        }}</label>
        <div class="mt-2.5">
          <input
            type="text"
            name="house-number"
            id="house-number"
            v-model="addressData.houseNumber"
            :placeholder="resourceText.addressHouseNumberPlaceholder"
            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
          />
        </div>
      </div>
      <div>
        <label for="house-number" class="block text-sm font-semibold leading-6 text-gray-900">{{
          resourceText.addressEdditionLabel
        }}</label>
        <div class="mt-2.5">
          <input
            type="text"
            name="house-number"
            id="house-number"
            v-model="addressData.eddition"
            :placeholder="resourceText.addressEdditionPlaceholder"
            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
          />
        </div>
      </div>
      <div class="sm:col-span-3">
        <label for="street" class="block text-sm font-semibold leading-6 text-gray-900">{{
          resourceText.addressStreetLabel
        }}</label>
        <div class="mt-2.5">
          <input
            type="text"
            name="street"
            id="street"
            v-model="addressData.street"
            :placeholder="resourceText.addressStreetPlaceholder"
            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
          />
        </div>
      </div>
      <div class="sm:col-span-3">
        <label for="place" class="block text-sm font-semibold leading-6 text-gray-900">{{
          resourceText.addressPlaceLabel
        }}</label>
        <div class="mt-2.5">
          <input
            type="text"
            name="place"
            id="place"
            v-model="addressData.place"
            :placeholder="resourceText.addressPlacePlaceholder"
            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
          />
        </div>
      </div>
    </div>
    <div class="mt-10">
      <button
        type="submit"
        class="block w-full rounded-md bg-indigo-600 px-3.5 py-2.5 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
      >
        {{ resourceText.addressButtonText }}
      </button>
    </div>
  </div>
</template>
