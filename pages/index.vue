<template>
  <div class="flex h-screen overflow-hidden bg-gray-50">
    <!-- Off-canvas menu for mobile -->
    <mobile-menu :mobile-open.sync="mobileOpen" />

    <!-- Static sidebar for desktop -->
    <static-sidebar />

    <div class="flex flex-col flex-1 w-0 overflow-hidden">
      <div class="relative z-10 flex flex-shrink-0 h-16 bg-transparent">
        <!-- Open sidebar button -->
        <button
          class="px-4 text-gray-500 focus:outline-none focus:bg-gray-100 focus:text-gray-600 md:hidden"
          aria-label="Open sidebar"
          @click="mobileOpen = true"
        >
          <svg
            class="w-6 h-6"
            stroke="currentColor"
            fill="none"
            viewBox="0 0 24 24"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h7"
            />
          </svg>
        </button>

        <div class="flex justify-between flex-1 mr-4 md:px-4">
          <div class="flex flex-1">
            <div class="flex items-center w-full md:ml-0">
              <label for="search_field" class="sr-only">Search</label>
              <div
                class="relative w-full text-gray-400 focus-within:text-gray-600"
              >
                <div
                  class="absolute inset-y-0 left-0 flex items-center ml-2 pointer-events-none"
                >
                  <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 20 20">
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
                    />
                  </svg>
                </div>
                <input
                  id="search_field"
                  class="items-center block w-full py-2 pl-8 pr-3 text-gray-900 placeholder-gray-500 border-2 border-gray-200 rounded-lg focus:outline-none focus:placeholder-gray-400 sm:text-sm"
                  placeholder="Search"
                  type="search"
                  autocomplete="off"
                />
              </div>
            </div>
          </div>
          <div class="flex items-center ml-2 md:ml-6">
            <button
              class="p-1 text-gray-400 rounded-full hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:shadow-outline focus:text-gray-500"
              aria-label="Notifications"
            >
              <svg
                class="w-6 h-6"
                stroke="currentColor"
                fill="none"
                viewBox="0 0 24 24"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
                />
              </svg>
            </button>

            <!-- Profile dropdown -->
            <div class="relative ml-3">
              <profile-dropdown />
            </div>
          </div>
        </div>
      </div>

      <main
        class="relative z-0 flex-1 py-6 overflow-y-auto md:pr-4 focus:outline-none"
        tabindex="0"
      >
        <div class="px-4 mx-auto max-w-7xl">
          <h1 class="text-2xl font-semibold text-gray-900">Dashboard</h1>
        </div>
        <div class="px-4 mx-auto max-w-7xl">
          <!-- Replace with your content -->
          <div class="py-4">
            <div
              class="bg-white border-4 border-gray-200 border-dashed rounded-lg h-96"
            ></div>
          </div>
          <!-- /End replace -->
        </div>
      </main>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import MobileMenu from '~/components/MobileMenu.vue'
import StaticSidebar from '~/components/StaticSidebar.vue'
import ProfileDropdown from '~/components/ProfileDropdown.vue'
export default Vue.extend({
  components: {
    MobileMenu,
    StaticSidebar,
    ProfileDropdown
  },
  data() {
    return {
      mobileOpen: false
    }
  }
})
</script>
