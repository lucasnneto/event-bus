<template>
  <v-container>
    <v-row>
      <v-col cols="12" sm="4" md="4" align-self="center" class="text-center">
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Banana"
          value="Banana"
          color="yellow darken-1"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Maça"
          value="Maça"
          color="error"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Pera"
          value="Pera"
          color="yellow"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Melancia"
          value="Melancia"
          color="green darken-1"
        ></v-checkbox>
      </v-col>
      <v-col cols="12" sm="4" md="4" align-self="center" class="text-center">
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Mamão"
          value="Mamão"
          color="orange darken-2"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Melão"
          value="Melão"
          color="yellow"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Morango"
          value="Morango"
          color="red"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Uva"
          value="Uva"
          color="purple"
        ></v-checkbox>
      </v-col>
      <v-col cols="12" sm="4" md="4" align-self="center" class="text-center">
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Laranja"
          value="Laranja"
          color="orange"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Limão"
          value="Limão"
          color="green"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Kiwi"
          value="Kiwi"
          color="green"
        ></v-checkbox>
        <v-checkbox
          v-model="itensParaCompra"
          @change="AdicionarALista"
          label="Abacaxi"
          value="Abacaxi"
          color="yellow darken-1"
        ></v-checkbox>
      </v-col>
    </v-row>
  </v-container>
</template>
<script lang="ts">
import Vue from "vue";
import { ref } from "vue";
import { bus } from "@/mixins/bus";
export default Vue.extend({
  name: "grupo-checkbox",

  setup(_, ctx) {
    const itensParaCompra = ref<string[]>([]);

    function AdicionarALista(fruta: any) {
      bus.$emit("lista-frutas", fruta);
    }

    return {
      itensParaCompra,
      AdicionarALista,
    };
  },
});
</script>
