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
const biografia = ref("")
const linguagem = ref("")

function a(e){
  if(senha.value === senhaconfirmaçao.value){
mostrar.value = true
}
else
alert ('senha invalida')
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
<div class="container">
  
  <div class="info" v-if="mostrar">
    <h2>Suas Informações</h2>
    <hr>
<p>Seu nome cadastrado é {{ nome }}</p>
<p>Seu email cadastrado foi {{ email }}</p>
<p>Sua idade cadastrado é {{ idade }}</p>
<p>Sua senha cadastrado é {{ senha }}</p>
<p>Sua senha cadastrado é {{ senhaconfirmaçao }}</p>
<p>Seu endereço foi cadastrado como {{ endereco }}</p>
<p>Sua cidade foi cadastrado como {{ cidade }}</p>
<hr>
<p>Biografia</p>
<p class="bio">{{ biografia }}</p>
</div>
  <form class="css" @submit.prevent="a" v-else>


<div class="login">
  <h2 class="titulo">Informe seu login</h2>
  <hr>
  <input type="text" v-model="nome" placeholder="Nome completo" minlength="3" maxlength="20" required>
<input type="email" v-model="email" placeholder="Email completo" minlength="3" maxlength="20" required>
<input type="dat" v-model="idade" placeholder="Informe sua idade" minlength="1" maxlength="3" required>
<input type="password" v-model="senha" placeholder="Senha" minlength="3"  required>
<input type="password" v-model="senhaconfirmaçao" placeholder="Confirma sua senha" minlength="1" required>
<input type="text" v-model="endereco" placeholder="Digite seu endereço"  required>
<input type="text" v-model="cidade" placeholder="Informe sua cidade"  required>
<input type="text" v-model="linguagem" placeholder="Linguagem de programação"  required>

<textarea v-model="biografia" cols="23" rows="10"></textarea>

<select v-model="estado">
<label>

</label>

{{ error }}
<label for="estado">estado
</label>
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

<select v-model="estado">
</select>
</select>
<p>
  <button  type="submit">Enviar</button>
</p>
</div>
</form>


</div>
</template>

<style scoped>

.bio{
  line-break: anywhere;
  word-wrap: break-word;
}
.css{
  display: grid;
  grid-template-columns: 1fr;
}
input{
  margin-top: 10px;
  border-radius: 12px;
}
select{
  margin-top: 10px;
  border-radius: 12px;
}
button{
  margin-top: 10px;
  border-radius: 12px;
}
textarea{
  margin-top: 10px;
  border-radius: 12px;
}
.login{
  margin-top: 20px;
  justify-content: center;
  text-align: center;
  background-color: black;
  color: rgb(255, 255, 255);
  border-radius: 15px;
  width: 280px;
  
  
}
.info{
  margin-top: 20px;
  justify-content: center;
  text-align: center;
  background-color: black;
  color: white;
  border-radius: 15px;
  width: 400px;
  height: 600px;
  padding: 20px;
}
.container{
  display: flex;
  justify-content: space-around;
  width: 100%;
}
p{
  margin-top: 10px;
}
.titulo{
  font-size: 30px;
  margin-top: 8px;
}

</style>
