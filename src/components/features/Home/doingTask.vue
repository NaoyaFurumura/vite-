<template>
  <TaskRowLayout>
    <TaskRowHeader title="Doing" class="doing-header" />
    <draggable v-model="tasks" item-key="id" group="tasks">
      <template #item="{ element }">
        <el-card shadow="always">{{ element.title }}</el-card>
      </template>
    </draggable>
  </TaskRowLayout>
</template>
<script lang="ts">
import { defineComponent, PropType, ref } from "vue";
import TaskRowLayout from "@/components/ui/HomeLayout/rows/index.vue";
import draggable from "vuedraggable";
import TaskRowHeader from "@/components/ui/HomeLayout/rows/header.vue";

export default defineComponent({
  components: {
    TaskRowLayout,
    draggable,
    TaskRowHeader,
  },
  props: {
    tasks: {
      type: Array as PropType<Array<{ id: string; title: string }>>,
    },
  },
  setup(props) {
    const tasks = ref(props.tasks);
    return {
      tasks,
    };
  },
});
</script>
<style lang="scss" scoped>
:deep(.task-row-header) {
  margin-bottom: 20px;
}
div.doing-header :deep(.el-card) {
  background: rgb(211, 229, 239);
  font-weight: 700;
  font-size: 23px;
}
</style>
