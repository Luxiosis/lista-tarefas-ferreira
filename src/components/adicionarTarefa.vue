<template>
    <div class="input-group">
      <!-- <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text" /> -->
      <!-- <entrada-dados :value="novaTarefa" @input="associarValor" /> -->
      <entrada-dados @salvar="adicionarTarefa" v-model="novaTarefa" />
      <span class="input-group-btn">
        <button @click="adicionarTarefa" class="btn btn-primary">
          Adicionar novas tarefas
        </button>
      </span>
    </div>
</template>

<script>
import entradaDados from '@/components/templates/entradaDados'
export default {
    components: { entradaDados },
    data() {
        return {
            novaTarefa: "",
        };
    },
    methods: {
        adicionarTarefa() {
            this.$emit("adicionarTarefa", this.novaTarefa);
            this.novaTarefa = "";
        },
        // associarValor(valor) {
        //    this.novaTarefa = valor;
        //},
    },
};
</script>

<style>

</style>