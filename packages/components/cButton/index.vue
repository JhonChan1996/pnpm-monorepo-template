<template>
  <a-button type="primary" @click="onButtonClick"
    >custom button version:{{ packageConfig.version }}</a-button
  >
</template>

<script setup>
import packageConfig from "../package.json";
const onButtonClick = () => {
  console.log("button clicked");
};
</script>
