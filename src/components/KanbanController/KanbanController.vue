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
                addFormVisible: false
            }
        },
        methods: {
            addTask(taskData) {
              this.boards[0].tasks.push(taskData)
            },

            closeCard() {
                this.addFormVisible = false;
            },

            addButtonClick() {
                this.addFormVisible = true;
            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>