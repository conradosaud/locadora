<script setup>

    /*
        Roteiro:

        ---- PARTE 1: introdução a consulta API
        1 - Mostrar PokeAPI
        2 - Interpretar o JSON manualmente
        3 - Apresentar e instalar o Axios
        4 - Função simples de consulta usando GET
        5 - Apresentar async/await
        6 - Ler a resposta do console
        7 - Usar REF na variável e exibir resposta no HTML
        8 - Mostrar como demora para o elemento ser carregado
        9 - Apresentar o onMounted
        10 - Apresentar o nome do pokemon no HTML

        ---- PARTE 2: apresentar pokemon completo
        1 - Montar um objeto com dados do pokemon
        2 - ATIVIDADE: montar o objeto com bae no JSON
        3 - ATIVIDADE: exibir os dados na tela
        4 - Mostrar imagem com v-bind:src

        // Se der tempo:
        ---- Operador ternário
        ---- Consulta na API do projeto

    */

   

    import axios from 'axios';

    let data = ref("calma carai");
    const pokemon = reactive({
        id: 0,
        nome: "",
        habilidade: "",
        imagem: ""
    })

    async function get(){
        
        const resposta = await axios.get("https://pokeapi.co/api/v2/pokemon/pikachu")
        data.value = resposta.data;

        pokemon.id = resposta.data.id;
        pokemon.nome = resposta.data.name;
        pokemon.habilidade = resposta.data.abilities[0].ability.name
        pokemon.imagem = resposta.data.sprites.front_shiny

    }    

    onMounted(()=>{
        get();
    })

</script>

<template>
    <h1>Teste da PokeAPI</h1>
    <button v-on:click="chama()">xaxaxa</button>
    <div>
        <p>ID: {{ pokemon.id }} </p>
        <p>Nome: {{ pokemon.nome }} </p>
        <p>Habilidade principal: {{ pokemon.habilidade }} </p>
        <img v-bind:src="pokemon.imagem" />
    </div>
</template>