<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        <p>Nome de usuário: <strong>{{ nome }}</strong> </p>
        <p>Idade do Usuário: <strong>{{ idade }}</strong> </p>        
        <button @click="reniciarNome">Reniciar Nome</button>

    </div>
</template>

<script>
import barramento from '@/barramento'

export default {
    props: ['nome', 'idade'],
    methods: {
        reniciarNome() {
            this.nome = 'Pedro'
            this.$emit('nomeMudou', this.nome)
        }
        

    },

    created() {
        barramento.quandoIdadeMudar(idade => {
            this.idade = idade
        } )
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
