<template>
  <main class="flex h-screen items-center justify-center bg-amber-300">
    <div class="flex flex-col rounded-2xl bg-amber-100 p-8">
      <div class="flex flex-col items-center justify-center">
        <h1 class="mb-2.5 text-4xl underline underline-offset-auto">
          <span class="font-bold">Palindrome</span> Checker
        </h1>
        <p>Enter a word to check if it is a palindrome</p>
      </div>
      <div class="flex justify-around">
        <input
          type="text"
          class="mt-5 rounded-sm border-1 p-2"
          placeholder="Enter a word"
          v-model="inputWord"
        />
        <button
          class="mt-5 rounded-sm border-1 bg-amber-500 p-2 hover:bg-amber-700"
          @click="checkPalindrome"
        >
          {{ buttonValue }}
        </button>
      </div>
      <div :class="[showResult ? 'block' : 'hidden']">
        <p class="mt-5 font-bold">Result:</p>
        <p v-if="inputWordInvalid" class="text-red-700">Please enter a word</p>
        <p v-else-if="isPalindrome" class="text-green-400">
          The word <span class="text-2xl font-bold">{{ inputWord }}</span> is a
          palindrome
        </p>
        <p v-else class="text-red-400">
          The word <span class="text-2xl font-bold">{{ inputWord }}</span> is not a
          palindrome
        </p>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      inputWord: "",
      showResult: false,
      buttonValue: "Check",
      isPalindrome: false,
    };
  },
  methods: {
    checkPalindrome() {
      if (this.showResult) {
        this.inputWord = "";
        this.showResult = false;
        this.buttonValue = "Check";
        this.isPalindrome = false;
        return;
      }

      const word = this.inputWord.toLowerCase().replace(/[^a-zA-Z0-9]/g, "");
      const reversedWord = word.split("").reverse().join("");
      this.isPalindrome = word === reversedWord;

      this.showResult = true;
      this.buttonValue = "Reset";
    },
  },
  computed: {
    inputWordInvalid() {
      return this.inputWord.trim() === "";
    },
  },
};
</script>
