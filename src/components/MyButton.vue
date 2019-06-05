<template>
  <button @click="onClick">
    <slot></slot>
  </button>
</template>

<script lang="ts">
import {Component, Prop, Emit, Vue} from "vue-property-decorator"

@Component
export default class MyButton extends Vue{
  private count: number = 0;

  @Prop() public greet?: string;

  @Emit() public clicked(count: number){}
  
  /**
   * onClick
   */
 public onClick() {
    // alert(this.greet);
    console.log(this.greet); //うっとおしいからコンソール出力に変更

    this.count++;
    this.clicked(this.count);
  }
}
</script>
