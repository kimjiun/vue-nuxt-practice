<template>
    <div>
        <div>{{ sendProps1 }}</div>
        <div>{{ sendProps2 }}</div>
        <div>{{ sendProps3.name }}</div>
        <div>{{ sendProps3.age }}</div>
    </div>
</template>

<script setup lang="ts">
import { toRefs } from 'vue';
import { Obj } from '../App.vue';

interface Props {
    sendProps1: String,
    sendProps2: Number,
    sendProps3: Obj
}

const props = defineProps<Props>()
const { sendProps1, sendProps2, sendProps3} = toRefs(props)
</script>

<style lang="scss" scoped>

</style>