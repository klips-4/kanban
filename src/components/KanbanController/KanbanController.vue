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
                        background: '#eee',
                        tasks: []
                    },

                    {
                        title: 'В работе',
                        background: '#eee',
                        tasks: []
                    },

                    {
                        title: 'Тестирование',
                        background: '#eee',
                        tasks: []
                    },
                    {
                        title: 'Выполненные',
                        background: '#eee',
                        tasks: []
                    },
                ],
                addFormVisible: false
            }
        },
        methods: {
            addTask(taskData) {
              this.boards[0].tasks.push(taskData)
            },

            closeCard() {
                this.addFormVisible = false
            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>