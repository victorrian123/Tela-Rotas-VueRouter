<template>
    <div class="usuario">
        <h2>Usuarios</h2>
        <hr>
        <router-view />
        <button sucesso @click="irParaInicio">Voltar</button>
    </div>
</template>

<script>
export default {
    methods: {
        irParaInicio() {
            //this.$router.push('/')
            // this.$router.push({ path: '/' })
            this.$router.push({ path: 'inicio' })
        }
    }
}
</script>

<style>

</style>