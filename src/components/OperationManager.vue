<template>
  <section>
    <h1>BankVue</h1>
    <OperationTable :operations="operations" :remove="remove">
    </OperationTable>
    <OperationCreate :onSubmit="onSubmit"></OperationCreate>
    <table>
      <thead>

      </thead>
    </table>

  </section>
</template>

<script>
import OperationTable from "./OperationTable.vue";
import OperationCreate from "./OperationCreate.vue";

export default {
  name: "OperationManager",
  components: {
    OperationTable,
    OperationCreate
  },
  data(){
    return {
      operations: [
        { id: 1, date: "2018-03-01", name: "Casino"},
        { id: 2, date: "2018-02-10", name: "Uber"},
        { id: 3, date: "2018-01-21", name: "Medecin"},
      ]
    }
  },
  methods: {
    onSubmit(name){
      const lastOperation = this.operations[this.operations.length - 1];
      const id = lastOperation.id + 1;
      const date = new Date().toLocaleString();
      this.operations.push({
        id,
        date,
        name
      });
    },
    remove(operationToRemove){
      this.operations = this.operations.filter(operation => operation.id !== operationToRemove.id);
    }
  }
}
</script>

<style>
  h1 {
    color: aqua;
  }
</style>
