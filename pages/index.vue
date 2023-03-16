<template>
    <!-- isi -->
    <div
      class="bg-white rounded-2xl container mx-auto translate-y-[14vh] shadow-2xl scroll-mt-40"
    >
      <div class="mx-14 pt-6 font-inter grid grid-cols-3">
        <select
          v-model="lang"
          id="countries"
          class="bg-gray-50 border border-gray-300 text-gray-900 text-xl rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full px-5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 mx-2"
        >
          <option selected>Choose a language</option>
          <option value="US">English</option>
          <option value="ID">Indonesia</option>
          <option value="CA">Canada</option>
          <option value="FR">France</option>
          <option value="DE">Germany</option>
          <option value="ja-JP">Japanese</option>
        </select>
        <!--Switch-->
        <button type="button" class="rounded-full bg-slate px-4">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-14 h-14 mx-auto rounded-full bg-slate-300 p-3 hover:bg-gray-400 transform active:scale-75 transition-transform"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M7.5 21L3 16.5m0 0L7.5 12M3 16.5h13.5m0-13.5L21 7.5m0 0L16.5 12M21 7.5H7.5"
            />
          </svg>
        </button>
        <select
          v-model="lang"
          id="countries"
          class="bg-gray-50 border border-gray-300 text-gray-900 text-xl rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full px-5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500 -mx-2"
        >
          <option selected>Choose a language</option>
          <option value="US">English</option>
          <option value="ID">Indonesia</option>
          <option value="CA">Canada</option>
          <option value="FR">France</option>
          <option value="DE">Germany</option>
          <option value="ja-JP">Japanese</option>
        </select>
      </div>

      <!--tabel bahasa-->
      <div class="mt-4 mx-8 mb-8 p-2 font-inter grid grid-cols-2 gap-2">
        <textarea
          v-model="text"
          cols="50"
          rows="10"
          class="mx-6 p-4 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-blue-500 focus:ring-blue-400 rounded-md sm:text-xl focus:ring-1"
          placeholder="Input text... "
        ></textarea>
        <textarea
          v-model="text"
          cols="50"
          rows="10"
          class="mx-6 p-4 bg-white border shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-blue-500 focus:ring-blue-400 rounded-md sm:text-xl focus:ring-1"
          placeholder="Input text..."
        ></textarea>
      </div>

      <!--Submit-->
      <div class="mx-10 mb-8 pb-9 font-inter grid grid-cols-5">
        <label></label>
        <!-- voice -->
        <button>
          <svg
            @click="speak"
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-14 h-14 mx-auto rounded-full bg-slate-300 p-4 hover:bg-gray-200 transform active:scale-75 transition-transform"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M19.114 5.636a9 9 0 010 12.728M16.463 8.288a5.25 5.25 0 010 7.424M6.75 8.25l4.72-4.72a.75.75 0 011.28.53v15.88a.75.75 0 01-1.28.53l-4.72-4.72H4.51c-.88 0-1.704-.507-1.938-1.354A9.01 9.01 0 012.25 12c0-.83.112-1.633.322-2.396C2.806 8.756 3.63 8.25 4.51 8.25H6.75z"
            />
          </svg>
        </button>
        <!-- submit -->
        <button
          @click=""
          type="submit"
          class="text-white hover:bg-blue focus:ring-4 focus:outline-none focus:ring-blue-900 font-medium rounded-lg text-base w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-900 dark:hover:bg-blue-800 dark:focus:ring-blue-900 transform active:scale-75 transition-transform"
        >
          Submit
        </button>
        <button>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-14 h-14 mx-auto rounded-full bg-slate-300 p-4 hover:bg-gray-200 transform active:scale-75 transition-transform"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M3 16.5v2.25A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75V16.5M16.5 12L12 16.5m0 0L7.5 12m4.5 4.5V3"
            />
          </svg>
        </button>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      text: "",
      lang: "US",
    };
  },
  methods: {
    speak() {
      const msg = new SpeechSynthesisUtterance();
      msg.text = this.text;
      msg.lang = this.lang;
      window.speechSynthesis.speak(msg);
    },
  },
};
</script>
