<template>
    <div>
        <input type="text" v-model="inputValue1"/>
        <div>{{  inputValue1 }}</div>

        <input type="text" :value="inputValue2" @input="inputValue2 = $event.target.value"/>
        <!-- onChange -->
        <div>{{  inputValue2 }}</div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            inputValue1: '',
            inputValue2: '',
        }
    },
}
</script>

<style lang="scss" scoped>

</style>