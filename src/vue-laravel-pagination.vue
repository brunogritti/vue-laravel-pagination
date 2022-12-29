<template>
<div class="btn-paginate">
    <small> Mostrando {{from}} - {{to}} de {{total}} encontrados.</small>
    <button class="btn" :disabled="from != 1"
        @click="prevPage">&laquo; Anterior
    </button>
    <button class="btn" :disabled="to != total"
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
            this.$emit('previous');
        },

        nextPage: function(){
            this.page++;
            this.$emit('next');
        },
        
        setPage: function(page){
            this.page = page;
        },
    }
}
</script>

<style lang="scss" scoped></style>