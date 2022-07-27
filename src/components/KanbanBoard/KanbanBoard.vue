<template src="./template.html">

</template>

<script>

    import KanbanCard from "@/components/KanbanCard/KanbanCard";

    export default {
        props: ['elementIndex', 'data',
            'lastBoard', 'firstBoard'],
        name: "KanbanBoard",
        components: {KanbanCard},
        methods: {
            addButtonClick() {
                this.$emit('addButtonClick')
            },
            notifyHandler(eventName,taskId) {
                this.$emit(eventName, taskId, this.elementIndex)
            }
        },

    }
</script>

<style scoped src="./Style.less" lang="less">

</style>