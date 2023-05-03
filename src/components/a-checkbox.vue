<template>
  <v-checkbox
    v-on="$listeners"
    v-bind="computedProps"
    hide-details="auto"
    @change="(e) => $emit('input', Boolean(e))"
  >
    <template v-slot:label>
      <slot></slot>
    </template>
  </v-checkbox>
</template>

<script lang="ts">
import { computed, defineComponent } from "vue";
export interface CheckboxDTO {
  indeterminate?: boolean;
  label: string;
  color: string;
  inputValue: boolean;
  disabled: boolean;
  readonly: boolean;
}

export default defineComponent({
  name: "a-Checkbox",
  props: {
    indeterminate: {
      default: false,
      type: Boolean,
    },
    label: {
      default: "",
      type: String,
    },
    color: {
      default: "primary",
      type: String,
    },
    disabled: Boolean,
    value: Boolean,
    readonly: Boolean,
  },

  setup(props) {
    const computedProps = computed<CheckboxDTO>(() => {
      let newProps: CheckboxDTO = {
        ...props,
        inputValue: props.value,
      };
      return newProps;
    });
    return { computedProps };
  },
});
</script>

<style lang="scss"></style>
