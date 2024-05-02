<template>
<div class="btn-paginate" v-if="total === 0">
  <small> Mostrando {{from}} - {{to}} de {{total}} encontrados.</small>
  <!-- Fazer classe dinamica com props -->
  <button class="btn" :disabled="from === 1" @click="prevPage">&laquo; Anterior
  </button>
  <button class="btn" :disabled="to === total" @click="nextPage">Próximo &raquo;
  </button>
</div>
</template>

<script>

import {ref} from "vue";

export default {
  props:['from', 'to', 'total'],
  setup(props, {emit}) {

    // let limit = ref(props.perPage ?? 10 );
    let page = ref(1);

    function prevPage(){
      page.value--;
      setPage(page.value);
      emit('page-changed', {page: page.value});
    }

    function nextPage(){
      page.value++;
      setPage(page.value);
      emit('page-changed', {page: page.value});
    }

    function setPage(page){
      page.value = page;
    }

    return {
      prevPage
    }
  }
}
</script>

<style lang="scss" scoped></style>