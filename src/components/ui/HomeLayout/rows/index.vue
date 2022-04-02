<template>
  <el-container>
    　<el-main>
      <slot></slot>
    </el-main>
  </el-container>
</template>
<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "TaskRowLayout",
});
</script>
