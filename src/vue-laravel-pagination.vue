<template>
<div class="btn-paginate">
    <!-- Fazer v-if pra ocultar essa seção -->
    <small> Mostrando {{from}} - {{to}} de {{total}} encontrados.</small>
    <!-- Fazer classe dinamica com props -->
    <button class="btn" :disabled="from == 1"
        @click="prevPage">&laquo; Anterior
    </button>
    <button class="btn" :disabled="to == total"
        @click="nextPage">Próximo &raquo;
    </button>
</div>
</template>

<script>
export default {
    props:['from', 'to', 'total', 'perPage'],
    data() {
      	return {
            limit: this.perPage || 10,
            page: 1
      	};
    },

    methods: {
        prevPage: function(){
            this.page--;
            this.$emit('page-changed');
        },

        nextPage: function(){
            this.page++;
            this.$emit('page-changed');
        },
        
        setPage: function(page){
            this.page = page;
        },
    }
}
</script>

<style lang="scss" scoped></style>