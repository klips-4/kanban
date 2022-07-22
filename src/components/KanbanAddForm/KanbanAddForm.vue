<template src="./template.html">

</template>

<script>
    export default {
        name: "KanbanAddForm",
        beforeMount() {
            this.task = {...this.defaultTask}
        },
        data() {
            return {
                task: null,
                defaultTask: {
                    title: '',
                    deadline: ''
                }
            }
        },

        methods: {
            closeForm() {
                this.task = null;
                this.$emit('close');
            },
            addTask(){
                this.$emit('addTask', {...this.task});
                this.task = null;
            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>