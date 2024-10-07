<script setup>

    const categorias = [
        { nome: "Ação", idade: 15 },
        { nome: "Suspense" },
        { nome: "Terror" },
        { nome: "Dorama" },
        { nome: "Comédia" },
        { nome: "Romance" },
        { nome: "Documentário" },
        { nome: "Drama" },
    ]

</script>

<template>

    <h1>Categorias de filmes</h1>

    <div v-for="categoria in categorias" >
        <p> categoria </p>
    </div>

</template>