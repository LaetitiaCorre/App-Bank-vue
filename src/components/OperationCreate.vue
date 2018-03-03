<template>
  <form @submit.prevent="onSubmit(name)" >
    <input v-model="name" type="text" name="operationName" placeholder="Operation Name">
    <button type="submit">Add</button>
  </form>
</template>

<script>

export default {
  name: "OperationCreate",
  data(){
    return {name:""};
  },

  props: {
    onSubmit: {
      type: Function,
      required: true
    }
  }
}

</script>

<style>

</style>
