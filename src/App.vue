<script setup>
import { ref } from 'vue'


const mostrar = ref(false)
const nome = ref('')
const email = ref('')
const idade = ref('')

</script>

<template>

<form class="email">
  <div class="login">

<label>nome</label>
<input type="text" v-model="nome"  minlength="3" maxlength="20" />
<hr>
<label>email</label>
<input type="email" v-model="email" minlength="3" maxlength="20" />
<hr>
<label>idade</label>
<input type="number" v-model="idade" minlength="1   " maxlength="20" />
<hr>
<button type="submit" @click.prevent="mostrar = !mostrar">CLique aqui</button>
</div>
<div v-if="mostrar">
<p>Seu nome registrado foi {{ nome }}</p>
<p>Seu nome registrado foi {{ email }}</p>
<p>Seu nome registrado foi {{ idade }}</p>
</div>

</form>

</template>

<style scoped></style>
