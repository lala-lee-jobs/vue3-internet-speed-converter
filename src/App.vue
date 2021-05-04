<template>
  <div class="container">
    <div class="card-header">Network Speed Convertere</div>
    <div class="card-body">
      <unit-control />
      <div class="converter">
        <div class="flex-1">
          <div class="converter-title">Set</div>
          <input type="number" class="input-number" min="0" :value="inputValue" @input="handleInputChange"/>
        </div>
        <span class="angle-icon fa-2x" style={{marginTop:30}}>
          <i class="fas fa-angle-right"></i>
        </span>
        <div class="text-right flex-1">
          <div class="converter-title">Show</div>
          <input type="text" class="input-number text-right" disabled :value="convertedValue"/>
        </div>
      </div>
    </div>
    <card-footer />
  </div>
</template>

<script>

import {ref, computed} from 'vue';
import CardFooter from './components/CardFooter';
import UnitControl from './components/UnitControl';

export default {
  name: 'App',
  components: {CardFooter, UnitControl},
  setup() {
    const inputValue = ref(0);
    const convertedValue = computed(() => inputValue.value / 8);
    const handleInputChange = (e) => {
      const {value} = e.target;
      inputValue.value = value;
    };
    return {
      inputValue,
      handleInputChange,
      convertedValue,
    };
  },
}
</script>

<style>
</style>
