<template>
   <div class="usuario-editar">
       <h3>Usuario Editar</h3>
       <hr>
       <p><strong>Codigo: </strong> Via ID: {{ id }} / Via Route: {{ $route.params.id }}</p>
       <p><strong>Completo: </strong> {{ $route.query.completo ? 'Sim' : 'Nao' }}</p>
       <p><strong>Lingua: </strong>{{ $route.query.lingua }}</p>
       <hr>
       <button primario @click="confirmou = true">Confirmar</button>
   </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return {
            confirmou: false
        }
    },
    beforeRouteLeave(to, from, next) {
        if (this.confirmou) {
            next()
        } else {
            if(confirm('Tem certeza?')) {
                next()
            } else {
                next(false)
            }
        }
    }
}
</script>

<style>

</style>