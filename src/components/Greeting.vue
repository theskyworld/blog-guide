<script setup lang="ts">
import { ref, computed } from "vue";

const { messages } = defineProps(["messages"]);

const greeting = ref(messages[0]);
function changeGreeting() {
  const randomMessage = computed(
    () => messages[Math.floor(Math.random() * messages.length)]
  );
  greeting.value = randomMessage.value;
}
</script>
<template>
  <div>
    <h3>{{ greeting }}! Thank you for visiting!</h3>
    <button @click="changeGreeting">New Greeting</button>
  </div>
</template>
<style scoped lang="scss"></style>
