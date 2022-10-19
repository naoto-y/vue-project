<script setup>
import TestComponent from '../components/TestComponent.vue';
import {onMounted, computed, watch, ref} from 'vue'

    const msg = ref('Hello!')
    const count = ref(0)
    const check = ref(false)
    const list = ['hoge', 'fuga', 'piyo']

    function log() {
        console.log(msg)
    }

    console.log('created')

    onMounted(() => {
        console.log('on mount');
    })
    
    const add = computed(() => {
        return msg.value + count.value;
    })

    watch(count, (count, prevCount) => {
        if (count % 2) {
            console.log('odd');
        } else {
            console.log('even');
        }
    })

</script>

<template>
    <div class="test">
        <TestComponent skill="9">
            <template #title>
                <h1>HTML5</h1>
            </template>
            <template #desc>
                <p>This is Markup Lnaguage</p>
            </template>
        </TestComponent>
        <TestComponent skill="7">
            <template #title>
                <h1>Vue.js</h1>
            </template>
            <template #desc>
                <p>This is a JavaScript FrameWork</p>
            </template>
        </TestComponent>
        <p><input type="text" v-model="msg"></p>
        <p class="msg">{{msg}}</p>
        <input type="checkbox" v-model="check" />
        <span v-if="check">true</span>
        <span v-else>false</span>
        <template v-for="(item, index) in list" :key="index">
            <p>{{item}}</p>
        </template>
        <p><button @click="count++">{{count}}</button></p>
        <p>{{add}}</p>
    </div>
</template>

<style scoped lang="scss">
.test {
    .msg {
        font-weight: bold;
    }
}
</style>