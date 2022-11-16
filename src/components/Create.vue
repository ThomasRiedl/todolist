<template>
  <form @submit.prevent="doCreate">
    <input type="text" v-model="item" placeholder="Add ToDo Item" />
    <button>Create</button>
  </form>
</template>

<script>
import { ref } from "vue";
export default {
  props: {
    create: { type: Function, required: true }
  },
  setup(props) {
    let item = ref("");
    function doCreate() {
      console.log("Create..." + item.value);
      props.create(item.value);
    }
    return { item, doCreate };
  }
};
</script>

<style scoped></style>