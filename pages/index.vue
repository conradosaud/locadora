<script setup>

    const filmes = reactive( [
        { 
            id: 0,
            nome: "Tropa de Elite",
            preco: 19.90,
            alugado: false,
        },
        { 
            id: 1,
            nome: "Matrix 1",
            preco: 30.90,
            alugado: false,
        },
        { 
            id: 2,
            nome: "O Matador",
            preco: 17.50,
            alugado: true,
        },
    ])

    function alteraAlugado( id ){
        filmes[id].alugado = true;
    }

</script>

<template>

    <Cabecalho/>

    <hr/>
    <p><strong>Filmes recomendados:</strong></p>

    <div class="conteudo" >
        <Filme v-for="filme in filmes" v-bind:filme="filme" v-bind:alteraAlugado="alteraAlugado" />
    </div>


</template>

<style>
    .conteudo{
        display: flex;
        gap: 20px;
    }
</style>