<template>
  <div>
    <PropsTestComponent :sendProps1="title" :sendProps2="createAt" :sendProps3="obj"/>
    <EmitTestComponent @send-event="parentEvent"/>

    <VModeltestComponent/>
  </div>
</template>

<script setup lang="ts">
import { reactive, ref } from 'vue';
import PropsTestComponent from './components/PropsTestComponent.vue';
import EmitTestComponent from './components/EmitTestComponent.vue';
import VModeltestComponent from './components/VModeltestComponent.vue';

export interface Obj {
  age: number
  name: string
}

const title = ref<string>('부모 컴포넌트에서 선언된 데이터 입니다.')
const createAt = ref<number>(2025)
const obj = reactive({
  age: 33,
  name: 'John'
})

const parentEvent = (event: string) => {
  console.log(event)
  title.value = event
}
</script>

<style lang="scss" scoped>

</style>