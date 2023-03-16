<template>
  <nav
    class="px-2 sm:px-4 py-2.5 dark:bg-gray-500 fixed w-full z-20 top-0 left-0 border-b border-gray-200 dark:border-gray-500 bg-white"
  >
    <div class="container flex flex-wrap items-center justify-between mx-auto">
      <!-- logo -->
      <NuxtLink
        to="/"
      >
        <div class="flex items-center">
          <img
            src="~/assets/logo.png"
            class="mr-4 sm:h-11"
            alt="Translateasy logo"
          />
          <span
            class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"
            >Translateasyy</span
          >
        </div>
      </NuxtLink>

      <!-- language -->
      <div class="flex md:order-2">
        <select
          id="countries"
          class="text-black hover:bg-blue focus:ring-4 focus:outline-none focus:ring-blue-900 text-sm rounded-lg focus:border-blue-100 block w-full p-2.5 dark:bg-blue-900 dark:hover:bg-blue-800 dark:focus:ring-blue-900"
        >
          <!-- text-white hover:bg-blue focus:ring-4 focus:outline-none focus:ring-blue-900 font-medium rounded-lg text-base w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-900 dark:hover:bg-blue-800 dark:focus:ring-blue-900 -->
          <option selected>Indonesia</option>
          <option value="US">English</option>
        </select>
      </div>
      <div
        class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1 text-black"
        id="navbar-sticky"
      >
        <ul
          class="flex flex-col p-4 mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium"
        >
          <li>
            <NuxtLink to="/" class="block py-2 pl-3 pr-4 text-black md:p-0 hover:text-gray-500"
              >Translator</NuxtLink
            >
          </li>
          <li>
            <NuxtLink
              to="/about"
              class="block py-2 pl-3 pr-4 text-black md:p-0  hover:text-gray-500"
              >About</NuxtLink
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      show: false,
    };
  },
};
</script>
