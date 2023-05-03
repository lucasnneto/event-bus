<template>
  <v-select
    v-on="$listeners"
    :items="lista"
    class="a-select"
    dense
    outlined
    multiple
    label="Lista de compras"
  >
  </v-select>
</template>
<style></style>
<script lang="ts">
import { defineComponent, onMounted, ref } from "vue";
import { bus } from "@/mixins/bus";
export default defineComponent({
  name: "a-select",

  setup(props) {
    onMounted(() => {
      bus.$on("lista-frutas", (fruta: any) => {
        lista.value = fruta;
      });
    });

    const lista = ref<string[]>([]);

    return { lista };
  },
});
</script>
<style>
.v-text-field--outlined.v-input--dense.v-text-field--outlined
  > .v-input__control
  > .v-input__slot {
  min-height: 36px !important;
  height: 36px;
}
.v-select:not(.error--text) .v-select__selections,
i.v-icon.notranslate.mdi.mdi-chevron-down.theme--light {
  color: #2f54d3;
}
.v-select:not(.error--text) .v-input__slot fieldset {
  border-color: #00000033;
}
.v-select.v-input--is-dirty:not(.error--text) .v-input__slot fieldset {
  border-color: #1f80e180 !important;
}

.v-input--is-disabled fieldset {
  background: #0000000d;
}
.v-input--is-disabled .v-select__selections {
  color: #00000080 !important;
}
.v-input.v-select fieldset {
  background: #fff;
}
.v-input.v-input--is-label-active.v-input--is-dirty.v-input--is-disabled.v-input--dense.theme--light.v-text-field.v-text-field--is-booted.v-text-field--enclosed.v-text-field--outlined.v-select
  fieldset {
  background-color: #0000000d !important;
}
.blueplaceholder .v-select__selections ::placeholder {
  color: #2f54d3 !important;
}
.v-select .v-list-item--active p {
  color: rgba(0, 0, 0, 0.87) !important;
}
.v-menu__content.theme--light.menuable__content__active {
  transform: translate(0px, 35px);
}
</style>
