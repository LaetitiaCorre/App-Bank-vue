<template>
  <div>
    <h1>Je suis</h1>
    <table>
      <thead>
        <th>Id</th>
        <th>Date</th>
        <th>Name</th>
        <th></th>
      </thead>
      <tbody>
        <tr v-for="operation of operations" :key="operation.id">
          <td>{{operation.id}}</td>
          <td>{{operation.date}}</td>
          <td>{{operation.name}}</td>
          <td><button @click="remove(operation)"  type="button">remove</button></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "OperationTable",
  props: {
    operations: {
      type: Array,
      required: true
    },
    remove: {
      type: Function,
      required: true
    }
  }
};
</script>

<style>

</style>
