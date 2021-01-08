<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        
        <p>Nome de usuário: <strong>{{ nome }}</strong> </p>
        <button @click="reniciarNome">Reniciar Nome</button>

    </div>
</template>

<script>
export default {
    props: ['nome'],
    methods: {
        reniciarNome() {
            this.nome = 'Pedro'
            this.$emit('nomeMudou', this.nome)
        }

    }
    
    
}
</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #ec485f;
        color: #fff;
    }
</style>
