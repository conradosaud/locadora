<script setup>

    // Pega os parâmetros que foram passados
    //const params = useAttrs(); // Pega 1 variável apenas
    const params = defineProps(["filme", "alteraAlugado"]); // Pega todo o objeto


</script>


<template>
    
    <div v-bind:class="{conteudo: true}">

        <p> {{ params.filme.nome }} </p>
        <p v-if="params.filme.alugado == true"><u>ALUGADO</u></p>
        <img src="https://placeholder.co/150"/>
        <p> {{ params.filme.preco }} </p>
        <button v-on:click="params.alteraAlugado( params.filme.id )" v-if="params.filme.alugado == false" class="botao">Alugar</button>

    </div>


</template>

<style scoped>
    
    .conteudo{
        display: flex;
        flex-direction: column;
        width: 200px;
        text-align: center;
        background-color: blueviolet;
        padding: 15px;
        color: #FFF;
        gap: 10px;
        border-radius: 10px;
    }

    .botao{
        background-color: orange;
        color: white;
        padding: 10px;
        border: none;
    }

</style>