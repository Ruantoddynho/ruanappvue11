<script setup>
import { ref , computed } from 'vue'


const mostrar = ref(false)
const nome = ref('')
const email = ref('')
const idade = ref('')
const senha = ref('')
const senhaconfirmaçao = ref("")
const endereco = ref("")
const cidade = ref("")

function a(e){
  if(senha.value === senhaconfirmaçao.value)

{
mostrar.value = true
alert ('senha invalida')
}
}

const error = computed(() => {
  if(senha.value != senhaconfirmaçao.value){
  return 'senhas devem ser iguais'
}else{
  return null
}
})

</script>

<template>
<form @submit.prevent="a">

<input type="text" v-model="nome" placeholder="Digite seu nome" minlength="3" maxlength="20" required>
<input type="email" v-model="email" placeholder="Digite seu email" minlength="3" maxlength="20" required>
<input type="number" v-model="idade" placeholder="Digite sua idade" minlength="1" maxlength="3" required>
<input type="password" v-model="senha" placeholder="Digite sua senha" minlength="3"  required>
<input type="password" v-model="senhaconfirmaçao" placeholder="Confirma sua senha" minlength="1" required>
<input type="text" v-model="endereco" placeholder="Digite seu endereço"  required>
<input type="text" v-model="cidade" placeholder="Digite sua cidade"  required>

<select v-model="estado">
<label>

</label>

{{ error }}

<button type="submit">Enviar</button>
</select>
<label for="estado">estado
</label>
<select v-model="estado">
<option value="AC">Acre</option>
<option value="AL">Alagoas</option>
<option value="AP">Amapá</option>
<option value="AM">Amazonas</option>
<option value="BA">Bahia</option>
<option value="CE">Ceara</option>
<option value="DF">Distrito Federal</option>
<option value="ES">Espirito Santo</option>
<option value="GO">Goías</option>
<option value="MA">Maranhão</option>
<option value="MT">Mato Grosso</option>
<option value="MS">Mato Grosso do Sul</option>
<option value="MG">Minas Gerais</option>
<option value="PA">Para</option>
<option value="PB">Paraíba</option>
<option value="PR">Parańa</option>
<option value="PE">Pernambuco</option>
<option value="PI">Piauí</option>
<option value="RJ">Rio de Janeiro</option>
<option value="RN">Rio Grande do Norte</option>
<option value="RS">Rio Grande do Sul</option>
<option value="RO">Rondonia</option>
<option value="RR">Roraima</option>
<option value="SC">Santa Catarina</option>
<option value="SP">São Paulo</option>
<option value="SE">Sergipe</option>
<option value="TO">Tocantins</option>
</select>


<button type="submit" >Enviar</button>
</form>

<div v-if="mostrar">
<p>Seu nome cadastrado foi {{ nome }}</p>
<p>Seu email cadastrado foi {{ email }}</p>
<p>Sua idade cadastrado foi {{ idade }}</p>
<p>Sua senha cadastrado foi {{ senha }}</p>
<p>Sua senha cadastrado foi {{ senhaconfirmaçao }}</p>
<p>Seu endereço foi cadastrado como {{ endereco }}</p>
<p>Sua cidade foi cadastrado como {{ cidade }}</p>
</div>
</template>

<style scoped>
</style>
