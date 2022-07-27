<template src="./template.html">

</template>

<script>

    import KanbanBoard from "@/components/KanbanBoard/KanbanBoard";
    import KanbanAddForm from "@/components/KanbanAddForm/KanbanAddForm";

    export default {
        name: "KanbanController",
        components: {
            KanbanBoard, KanbanAddForm
        },
        data() {
            return {
                boards: [
                    {
                        title: 'В ожидании',
                        background: '#e76060',
                        cardBackground: '#eee',
                        tasks: []
                    },

                    {
                        title: 'В работе',
                        background: '#3ecbaf',
                        cardBackground: '#eee',
                        tasks: []
                    },

                    {
                        title: 'Тестирование',
                        background: '#8ad965',
                        cardBackground: '#eee',
                        tasks: []
                    },
                    {
                        title: 'Выполненные',
                        background: '#efb94d',
                        cardBackground: '#eee',
                        tasks: []
                    },
                ],
                addFormVisible: false,
                indexTask: 0

            }
        },
        methods: {
            addTask(taskData) {
                this.indexTask++;
                this.boards[0].tasks.push(taskData)
            },

            closeCard() {
                this.addFormVisible = false;
            },

            addButtonClick() {
                this.addFormVisible = true;
            },
            deleteTask(taskId, boardId) {
                const tasks = this.boards[boardId].tasks;
                const newTasks = [];

                tasks.forEach((item) => {
                  if(item.id !==taskId) {
                      newTasks.push(item);
                  }
                });

                this.boards[boardId].tasks = newTasks;
            },
            moveNextBoard(taskId, boardId) {
                const tasks = this.boards[boardId].tasks;
                const newTasks = [];
                let itemNew = null;

                tasks.forEach((item) => {
                    if (item.id !== taskId) {
                        newTasks.push(item);
                    } else {
                        itemNew = item;
                    }
                });
                this.boards[boardId + 1].tasks.push(itemNew);
                this.boards[boardId].tasks = newTasks;
            },
            movePrevBoard(taskId, boardId) {
                const tasks = this.boards[boardId].tasks;
                const newTasks = [];
                let itemNew = null;

                tasks.forEach((item) => {
                    if (item.id !== taskId) {
                        newTasks.push(item);
                    } else {
                        itemNew = item;
                    }
                });
                this.boards[boardId - 1].tasks.push(itemNew);
                this.boards[boardId].tasks = newTasks;
            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>