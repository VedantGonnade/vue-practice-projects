<template>
  <main
    class="flex h-screen items-center justify-center bg-blue-500 text-white"
  >
    <div class="flex flex-col rounded-lg p-8">
      <p>Get 25% Discount with this coupon</p>
      <div class="py-3">
        <input
          type="text"
          class="mr-4 rounded border bg-white py-1 text-center text-black"
          v-model="coupon"
        />
        <button
          class="cursor-pointer rounded border-1 px-3 py-1 text-center hover:bg-blue-800"
          @click="copyToClipboard"
        >
          {{ copyButtonText }}
        </button>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      coupon: "",
      copyButtonText: "Copy",
    };
  },
  methods: {
    copyToClipboard() {
      navigator.clipboard.writeText(this.coupon);
      this.copyButtonText = "Copied!";
      setTimeout(() => {
        this.copyButtonText = "Copy";
        this.coupon = "";
      }, 3000);
    },
  },
};
</script>
