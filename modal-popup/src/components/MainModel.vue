<template>
  <div>
    <PopUpModel v-if="isModalVisible" @close="closeModal"/>
    <div class="flex items-center justify-center text-white">
      <div class="flex h-64 w-1/4 flex-col items-center justify-center">
        <h1 class="text-4xl">
          <span class="text-4xl font-bold">Lets</span> Create a Modal
        </h1>
        <p class="mt-1">Click Button Below</p>
        <button
          @click="openModal"
          class="mt-5 rounded-sm border-1 p-2 hover:bg-amber-500 cursor-pointer"
        >
          TEST POPUP
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import PopUpModel from "@/components/PopUpModel.vue";

export default {
  name: "MainModel",
  components: { PopUpModel },
  data() {
    return {
      isModalVisible: false,
    };
  },
  methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
  },
};
</script>
