<script setup lang="ts">
import DefaultAuthCard from '@/components/Auths/DefaultAuthCard.vue'
import InputGroup from '@/components/Auths/InputGroup.vue'
import BreadcrumbDefault from '@/components/Breadcrumbs/BreadcrumbDefault.vue'
import DefaultLayout from '@/layouts/DefaultLayout.vue'
import DefaultLoginLayout from '@/layouts/DefaultLoginLayout.vue'
import CoverLogin from '@/assets/images/cover/cover-02.jpg'
import logoLogin from '@/assets/images/logo/logo.svg'
import '@fortawesome/fontawesome-free/css/all.css';

import { ref } from 'vue'

const pageTitle = ref('Sign In')

// State untuk mengontrol visibilitas password
const showPassword = ref(false)
</script>

<template>
  <DefaultLoginLayout>
    <div class="w-full flex flex-wrap">
      <!-- Login Section -->
      <div class="w-full md:w-1/2 flex flex-col">
        <div class="flex justify-center md:justify-start pt-12 md:pl-12 md:-mb-24">
          <a href="/" class="flex justify-center md:justify-start pt-12 md:pl-12 md:-mb-24">
            <img :src="logoLogin" alt="Logo" class="w-32 h-auto" />
          </a>
        </div>

        <div class="flex flex-col justify-center md:justify-start my-auto pt-8 md:pt-0 px-8 md:px-24 lg:px-32">
          <p class="text-center text-3xl">Welcome</p>
          <form class="flex flex-col pt-3 md:pt-8" onsubmit="event.preventDefault();">
            <div class="flex flex-col pt-4">
              <label for="username" class="text-lg">Username</label>
              <input
                type="text"
                id="username"
                placeholder="username"
                class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mt-1 leading-tight focus:outline-none focus:shadow-outline"
              />
            </div>

            <div class="flex flex-col pt-4 relative">
              <label for="password" class="text-lg">Password</label>
              <input
                :type="showPassword ? 'text' : 'password'"  
                id="password"
                placeholder="****"
                class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mt-1 leading-tight focus:outline-none focus:shadow-outline"
              />
              <button
                type="button"
                @click="showPassword = !showPassword"  
                class="absolute right-3 top-3 text-gray-600">
                <i :class="showPassword ? 'fas fa-eye-slash' : 'fas fa-eye'"></i> <!-- Ikon mata -->
              </button>
            </div>

            <button
              type="submit"
              class="bg-blue-700 text-white font-bold text-lg hover:bg-gray-700 p-2 mt-8">
              Log In
            </button>
          </form>
          <div class="text-center pt-12 pb-12">
            <a href="" class="underline font-semibold">
              <p>Forgot Password?</p>
            </a>
          </div>
        </div>
      </div>

      <!-- Image Section -->
      <div class="w-1/2 shadow-2xl">
        <img
          class="object-cover w-full h-screen hidden md:block"
          :src="CoverLogin"
          alt="Login Cover"
        />
      </div>
    </div>
  </DefaultLoginLayout>
</template>

<style scoped>
/* Styling tambahan untuk ikon mata */

</style>
