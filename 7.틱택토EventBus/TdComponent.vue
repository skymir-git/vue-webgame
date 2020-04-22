<template>
    <td @click="onClickTd">{{cellData}}</td>
</template>

<script>
    import EventBus from "./EventBus";
    export default {
        name: "TdComponent",
        props: {
            cellData: String,
            rowIndex: Number,
            cellIndex: Number,
        },
        methods: {
            onClickTd() {
                if (this.cellData) return;
                // EventBus.$on 호출
                EventBus.$emit('clickTd', this.rowIndex, this.cellIndex);
            }
        }
    }
</script>

<style>

</style>