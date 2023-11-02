<template>
  <div
    class="min-h-screen bg-gray-100 flex flex-col justify-center items-center"
  >
    <div class="bg-white p-6 rounded-lg shadow-lg">
      <h1 class="text-lg font-semibold mb-4">{{ message }}</h1>
      <button
        @click="changeMessage"
        class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-400 transition"
      >
        Change Message
      </button>
    </div>
  </div>
</template>

<script lang="ts" setup>
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  onErrorCaptured,
  onRenderTracked,
  onRenderTriggered,
} from "vue";

const message = ref("Hello, Vue 3 with <script setup> and TypeScript!");

const changeMessage = () => {
  message.value = "Message has been changed!";
};

onBeforeMount(() => {
  console.log("onBeforeMount: Component is about to be mounted");
});

onMounted(() => {
  console.log("onMounted: Component has been mounted");
});

onBeforeUpdate(() => {
  console.log("onBeforeUpdate: Component is about to update");
});

onUpdated(() => {
  console.log("onUpdated: Component has been updated");
});

onBeforeUnmount(() => {
  console.log("onBeforeUnmount: Component is about to be unmounted");
});

onUnmounted(() => {
  console.log("onUnmounted: Component has been unmounted");
});

onErrorCaptured((error) => {
  console.log("onErrorCaptured: An error has been captured", error);
  return false;
});

onRenderTracked((event) => {
  console.log(
    "onRenderTracked: A reactive dependency has been tracked during rendering",
    event,
  );
});

onRenderTriggered((event) => {
  console.log(
    "onRenderTriggered: A reactive dependency has been triggered (mutated)",
    event,
  );
});

console.log(
  "This runs when the component is being created, similar to the created lifecycle hook.",
);
</script>

<style scoped></style>
