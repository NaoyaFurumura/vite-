<template>
  <el-row>
    <el-col :span="3">
      <slot name="menu"></slot>
    </el-col>
    <el-col :span="7">
      <slot name="ReadyTaskRow"></slot>
    </el-col>
    <el-col :span="7">
      <slot name="DoingTaskRow"></slot>
    </el-col>
    <el-col :span="7">
      <slot name="DoneTaskRow"></slot>
    </el-col>
  </el-row>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HomeLayout",
});
</script>
