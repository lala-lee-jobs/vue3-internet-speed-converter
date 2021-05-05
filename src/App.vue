<template>
  <div class="container">
    <div class="card-header">Network Speed Convertere</div>
    <div class="card-body">
      <unit-control />
      <unit-converter v-model.number="inputValue"/>
    </div>
    <card-footer :input-value="Number(inputValue)"/>
  </div>
</template>

<script>

import {ref} from 'vue';
import CardFooter from './components/CardFooter';
import UnitControl from './components/UnitControl';
import UnitConverter from './components/UnitConverter';

export default {
  name: 'App',
  components: {CardFooter, UnitControl, UnitConverter},
  setup() {
    const inputValue = ref(0);
    return {
      inputValue,
    };
  },
}
</script>

<style>
</style>
