<template>
  <div>
    <v-container fluid>
      <group-checkbox></group-checkbox>
      <a-select></a-select>
    </v-container>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import groupCheckbox from "../components/groupCheckbox.vue";
import aSelect from "../components/a-select.vue";
export default Vue.extend({
  components: { groupCheckbox, aSelect },
  name: "HomeView",
});
</script>

<style>
.container {
  margin: auto;
  width: max-content;
  max-width: 90vw;
}
.container.container--fluid {
  width: 90vw;
}
</style>
