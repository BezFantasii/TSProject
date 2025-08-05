<template>
  <div class="dataModule">
    <div class="input__row">
      <InputText type="number" v-model.number="dataField.value1" placeholder="вес посылки"/>
      <InputText type="text" v-model="dataField.value2" placeholder="вес посылки"/>
    </div>
    <div class="input__row">
      <InputText type="text" v-model="dataField.value3" placeholder="вес посылки"/>
      <InputText type="text" v-model="dataField.value4" placeholder="вес посылки"/>
    </div>
  </div>
  <div>{{ dataField }}</div>
  <Button @click="checkValue(dataField)">Value</Button>
</template>

<script setup lang="ts">
import { reactive } from 'vue';
import InputText from 'primevue/inputtext';
import Button from 'primevue/button';

interface DataFields {
  value1: number | null;
  value2: string;
  value3: string;
  value4: string;
}

const dataField = reactive<DataFields>({
  value1: null,
  value2: '',
  value3: '', 
  value4: ''
});

function checkValue(value: DataFields) {
  console.log('Values:', {
    value1: typeof value.value1,
    value2: typeof value.value2,
    value3: typeof value.value3,
    value4: typeof value.value4
  }, value);
}
</script>

<style scoped>
.input__row {
  display: flex;
  justify-content: space-around;
  margin-bottom: 1rem;
}
.dataModule{
  width: 60%;
  padding: 20px;
  box-sizing: border-box;
  border-radius: 30px;
  background-color: aquamarine;
}
</style>