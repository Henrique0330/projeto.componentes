<script setup>

defineProps({
    dados: Object,
    mostrar: Boolean
})


</script>
<template>
    <div class="conteiner-resultado">
        <div class="resultado">
            <h1>Resultado</h1>
            <p>Nome: {{ dados.nome }}</p>
            <p>Email: {{ dados.email }}</p>
            <p>Senha: {{ dados.senha }}</p>
            <p>Confirmar senha: {{ dados.confirsenha }}</p>
            <p>Data de Nascimento: {{ dados.datanasc }}</p>
            <p>Endereço: {{ dados.endereco }}</p>
            <p>Cidade: {{ dados.cidade }}</p>
            <p>Estado: {{ dados.estado }}</p>
            <p>Hobie(s): <span v-for="hobie in dados.hobies" :key="hobie">{{ hobie + " " }}</span></p>
            <p>Linguagen(s) de Programação: <span v-for="linguagens in dados.linguagem" :key="linguagens">{{ linguagens + " " }}</span></p>
            <p>Biografia: <span> {{ dados.biografia }} </span></p>
        </div>
    </div>
</template>
<style scoped>
.conteiner-resultado {
    display: flex;
    justify-content: center;
}

.resultado {
    width: 60%;
    background-color: #ccc;
    border-radius: 10px;
    margin: 5%;
    display: flex;
    flex-direction: column;
}

.resultado p,
h1 {
    margin: 10px;
    word-wrap: break-word;
}
</style>