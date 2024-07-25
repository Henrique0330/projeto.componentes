<script setup>

defineProps({
  estados: Array
});

const emit = defineEmits(["dados"])

function save() {
  emit("dados", { ...dados })
}



import {
  reactive,
  ref
} from "vue"

const dados = reactive({
  nome: "",
  email: "",
  senha: "",
  confirsenha: "",
  datanasc: "",
  endereco: "",
  cidade: "",
  estado: "",
  hobies: [],
  linguagem: [],
  biografia: ""
});

const mostrarbotao = ref(false);

</script>

<template>
  <main>
    <div class="cadastro">
      <form @submit.prevent="save">
        <div class="info-inicial">
          <div><label for="nome">Nome</label>
            <input v-model="dados.nome" type="text" name="nome" placeholder=" Nome (Ex: Ruan)">
          </div>

          <div><label for="email">E-mail</label>
            <input v-model="dados.email" type="email" name="email" placeholder="Email (Ex: teste@gmail.com)">
          </div>

          <div><label for="senha">Senha</label>
            <input v-model="dados.senha" type="password" name="senha" placeholder="Senha (Ex: 123456)">
          </div>

          <div><label for="senha-confirmar">Confirmar Senha</label>
            <input v-model="dados.confirsenha" type="password" name="senha-confirmar"
              placeholder="Confirmar Senha (Ex: 123456)">
          </div>
        </div>

        <div class="info-secundaria">
          <div><label for="data-nasc">Data de Nascimento</label>
            <input v-model="dados.datanasc" type="date" name="data-nasc" placeholder="Data de Nascimento">
          </div>

          <div><label for="endereço">Endereço</label>
            <input v-model="dados.endereco" type="text" name="endereço"
              placeholder="Endereço (Ex: Rua do Jorge 123, Itinga)">
          </div>

          <div><label for="cidade">Cidade</label>
            <input v-model="dados.cidade" type="text" name="cidade" placeholder="Cidade (Ex: Joinvile)">
          </div>

          <div><label for="estado">Estado</label>
            <select v-model="dados.estado" name="estado">
              <option v-for="estado in estados" :key="estado" :value="estado.nome">{{ estado.sigla }}</option>
            </select>
          </div>
        </div>


        <!-- Hobbies -->
        <div class="hobies-e-linguagem">
          <div class="hobies">
            <h2>Seus hobies</h2>
            <div><input value="Esporte" v-model="dados.hobies" name="esporte" type="checkbox">
              <label for="esporte">Esporte</label>
            </div>

            <div> <input value="Jogos" v-model="dados.hobies" name="jogos" type="checkbox">
              <label for="jogos">Jogos</label>
            </div>

            <div><input value="Viagem" v-model="dados.hobies" name="viagem" type="checkbox">
              <label for="viagem">Viagem</label>
            </div>

            <div><input value="Culinaria" v-model="dados.hobies" name="culinaria" type="checkbox">
              <label for="culinaria">Culinária</label>
            </div>
          </div>
          <!-- End -->
          <!-- Linguagens de Programação -->
          <div class="linguagem">
            <h2>Linguagens de Programação</h2>
            <div>
              <input value="Javascript" v-model="dados.linguagem" name="javascript" type="checkbox">
              <label for="javascript">JavaScript</label>
            </div>

            <div>
              <input value="C#" v-model="dados.linguagem" name="c#" type="checkbox">
              <label for="c#">C#</label>
            </div>

            <div>
              <input value="Python" v-model="dados.linguagem" name="python" type="checkbox">
              <label for="python">Python</label>
            </div>

            <div><input value="Java" v-model="dados.linguagem" name="java" type="checkbox">
              <label for="java">Java</label>
            </div>
          </div>
          <!-- End -->
        </div>

        <div class="biografia">
          <h2>Biografia</h2>
          <textarea v-model="dados.biografia" class="bio" name="biografia" cols="150%" rows="10"></textarea>
        </div>
          <button class="conteiner-botao enviar-botao" type="submit" >Enviar</button>
      </form>
    </div>
  </main>

</template>

<style scoped>
form {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.cadastro {
  width: 90%;
  margin: 20px auto;
}

.info-inicial {
  margin: 80px;
  width: 60%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 70px;
  box-shadow: 0px 3px 0px rgb(206, 205, 205);
}

.info-inicial div input {
  width: 100%;
  height: 5vh;
  margin: 10px 0px 30px;
}

.info-secundaria {
  width: 60%;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 70px;
}

.info-secundaria div input {
  width: 100%;
  height: 5vh;
}

.info-secundaria div select {
  width: 100%;
  height: 5.4vh;

}

.hobies-e-linguagem {
  margin: 50px;
  display: flex;
  justify-content: space-between;
  width: 60%;
}

.hobies,
.linguagem {
  display: flex;
  align-items: center;
  flex-direction: column;
  gap: 10px;
}

.biografia {
  margin: 3%;
}

.bio {
  max-width: 55vw;
  max-height: 30vh;
}


.conteiner-botao {
  display: flex;
  width: 60%;
  flex-direction: column-reverse;
}

.botao-enviar {
  display: inline-block;
  padding: 10px 20px;
  background-color: #ccc;
  color: #333;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-decoration: none;
  transition: background-color 0.3s, color 0.3s;
  cursor: pointer;
}

.botao-enviar:hover {
  background-color: #505050;
  color: #fffafa;
}
</style>
