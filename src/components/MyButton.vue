<template>
  <button @click="onClick">{{buttonName}}</button>
</template>

<script lang="ts">
import {Component, Prop, Emit, Vue} from "vue-property-decorator"

@Component
export default class MyButton extends Vue{
  @Prop() public greet?: string;
  @Prop({default: "test"}) public buttonName!: string;

  @Emit() public clicked(){}
  
  /**
   * onClick
   */
 public onClick() {
    alert(this.greet);
    this.clicked();
  }
}
</script>
