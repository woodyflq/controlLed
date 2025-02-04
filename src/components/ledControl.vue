<script setup>
import axios from "axios";

const lambdaUrl = "https://boj3vfxwwdnwduzz7fsm2qoo5a0tmpoy.lambda-url.sa-east-1.on.aws/";

const sendCommand = async (command) => {
  try {
    const response = await axios.post(lambdaUrl, { command });
    console.log("Resposta da Lambda:", response.data);
    alert(response.data.message || "Comando enviado com sucesso!");
  } catch (error) {
    console.error("Erro ao chamar a Lambda:", error);
    alert("Erro ao enviar o comando.");
  }
};
</script>

<template>
  <div>
    <button @click="sendCommand('TurnOnIntent')">Ligar Luz</button>
    <button @click="sendCommand('TurnOffIntent')">Desligar Luz</button>
  </div>
</template>

<style scoped>
button {
  padding: 10px 20px;
  margin: 10px;
  font-size: 16px;
  background-color: #4caf50;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 5px;
}
button:hover {
  background-color: #45a049;
}
</style>
