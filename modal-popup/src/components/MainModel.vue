<template>
  <div class="h-screen bg-blue-500">
    <PopUpModel
      v-if="isModalVisible"
      @close="closeModal"
      :class="slideAnimation"
    />
    <div class="flex items-center justify-center text-white">
      <div class="flex h-64 w-1/4 flex-col items-center justify-center">
        <h1 class="text-4xl">
          <span class="text-4xl font-bold">Lets</span> Create a Modal
        </h1>
        <p class="mt-1">Click Button Below</p>

        <button
          @click="openModal"
          class="mt-5 cursor-pointer rounded-sm border-1 p-2 hover:bg-amber-500"
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
      slideAnimation: "slide-down",
    };
  },
  methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.slideAnimation = "slide-up";
      setTimeout(() => {
        this.slideAnimation = "slide-down";
        this.isModalVisible = false;
      }, 300);
    },
  },
};
</script>

<style scoped>
.slide-down {
  animation: slide 0.5s ease-out;
}
@keyframes slide {
  0% {
    transform: translateY(-30rem);
  }
  100% {
    transform: translateY(0);
  }
}

.slide-up {
  animation: slide-up ease 0.8s;
}

@keyframes slide-up {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-50rem);
  }
}
</style>
