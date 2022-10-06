<script setup>
    import {onMounted, ref} from 'vue'

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
</script>

<template>
    <div class="test">
        <p><input type="text" v-model="msg"></p>
        <p class="msg">{{msg}}</p>
        <input type="checkbox" v-model="check" />
        <span v-if="check">true</span>
        <span v-else>false</span>
        <template v-for="(item, index) in list" :key="index">
            <p>{{item}}</p>
        </template>
        <p><button @click="count++">{{count}}</button></p>
    </div>
</template>

<style scoped lang="scss">
.test {
    .msg {
        font-weight: bold;
    }
}
</style>