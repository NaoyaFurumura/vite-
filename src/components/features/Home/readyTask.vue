<template>
  <TaskRowLayout>
    <TaskRowHeader title="Ready" class="ready-header" />
    <draggable v-model="tasks" item-key="id" group="tasks">
      <template #item="{ element }">
        <el-card shadow="always" @click="clicked(element.id)">{{
          element.title
        }}</el-card>
      </template>
    </draggable>
  </TaskRowLayout>
</template>
<script lang="ts">
import { defineComponent, PropType, ref } from "vue";
import draggable from "vuedraggable";
import TaskRowLayout from "@/components/ui/HomeLayout/rows/index.vue";
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
    const clicked = (id: string) => {
      console.log(id);
    };
    return {
      tasks,
      clicked,
    };
  },
});
</script>
<style lang="scss" scoped>
:deep(.task-row-header) {
  margin-bottom: 20px;
}
div.ready-header :deep(.el-card) {
  background: rgb(211, 229, 239);
  font-weight: 700;
  font-size: 23px;
}
</style>
