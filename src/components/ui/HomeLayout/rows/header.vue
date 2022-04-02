<template>
  <div>
    <el-card shadow="never" class="task-row-header">{{ title }}</el-card>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    title: {
      type: String,
    },
  },
  name: "TaskRowHeader",
});
</script>
