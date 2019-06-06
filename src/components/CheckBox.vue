<template>
  <label class="checkbox">
    <input
      class="checkbox__input"
      type="checkbox"
      :value="value"
      :required="required"
    >
    <span class="checkbox__control" />
    <slot>{{ checked }}___{{ label }}</slot>
  </label>
</template>

<script script lang="ts">
import {Component, Prop, Watch, Model, Vue} from "vue-property-decorator"

@Component
export default class CheckBox extends Vue {
  @Prop({default: ''}) public label!: string;
  @Prop({default: true}) value!:boolean | number | string;
  @Prop({default: false}) required!:boolean;
}
</script>
