<script setup>
import LedControl from './components/ledControl.vue';

// Substitua pela URL correta da sua Lambda Function
const LAMBDA_URL = "https://boj3vfxwwdnwduzz7fsm2qoo5a0tmpoy.lambda-url.sa-east-1.on.aws/";

</script>

<template>
  <div>
    <LedControl />
  </div>
</template>
