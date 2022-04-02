<template>
  <HomeLayout>
    <template v-slot:menu>
      <HomeMenu />
    </template>
    <template v-slot:ReadyTaskRow>
      <ReadyTaskRow :tasks="readyTasks" />
    </template>
    <template v-slot:DoingTaskRow>
      <DoingTaskRow :tasks="doingTasks" />
    </template>
    <template v-slot:DoneTaskRow>
      <DoneTaskRow :tasks="doneTasks" />
    </template>
  </HomeLayout>
</template>
<script>
import { defineComponent } from "vue";
import HomeLayout from "@/components/ui/HomeLayout/homeLayout.vue";
import ReadyTaskRow from "@/components/features/Home/readyTask.vue";
import DoingTaskRow from "@/components/features/Home/doingTask.vue";
import DoneTaskRow from "@/components/features/Home/doneTask.vue";
import HomeMenu from "@/components/features/Home/menu.vue";
export default defineComponent({
  components: {
    HomeLayout,
    ReadyTaskRow,
    DoingTaskRow,
    DoneTaskRow,
    HomeMenu,
  },
  name: "Home",
  setup() {
    const readyTasks = [
      {
        id: 1,
        title: "ready 1",
      },
      {
        id: 2,
        title: "ready 2",
      },
    ];
    const doingTasks = [
      {
        id: 3,
        title: "doing1",
      },
      {
        id: 4,
        title: "doing2",
      },
    ];
    const doneTasks = [
      {
        id: 5,
        title: "done1",
      },
      {
        id: 6,
        title: "done2",
      },
    ];
    return {
      readyTasks,
      doingTasks,
      doneTasks,
    };
  },
});
</script>
