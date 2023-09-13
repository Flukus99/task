<template>
  <tasks-list />
</template>

<script>
import tasksList from "../components/TasksList";

export default {
  name: "HomePage",

  components: {
    tasksList,
  },
};
</script>
