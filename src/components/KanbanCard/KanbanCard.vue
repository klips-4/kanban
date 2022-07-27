<template src="./template.html">

</template>

<script>
    export default {
        name: "KanbanCard",
        props: ['color', 'data', 'elementIndex',
            'last', 'first'],
        methods: {
            notifyHandler(eventName) {
                this.$emit(eventName, this.data.id)
            }
        }
    }
</script>

<style scoped src="./Style.less" lang="less">

</style>