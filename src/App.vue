<script setup>
import { ref } from 'vue';

const inputValue = ref('');
const isRed = ref(false);

const handleChange = (event) => {
  inputValue.value = event.target.value;
};

const handleClick = () => {
  isRed.value = !isRed.value;
};
</script>

<template>
  <div>
    <p>Ketika Value lebih dari 10 maka tulisan membesar</p>
    <input style="margin-bottom: 10px ;" type="text" v-model="inputValue" @input="handleChange" />
    <div :class="{ 'red-text': inputValue.length > 5 }" :style="{ fontSize: inputValue.length > 10 ? '24px' : '16px', backgroundColor: inputValue }">
      {{ inputValue }}
    </div>
    <button style="margin-top: 10px; padding: 10px 20px; border-radius: 5px; font-size: 16px; color: white; background-color: #007bff; border: none; cursor: pointer;" @click="handleClick" :style="{ backgroundColor: isRed ? 'red' : '#007bff' }">Tekan Tombol</button>
  </div>
</template>

<style scoped>
.red-text {
  color: red;
}
</style>
