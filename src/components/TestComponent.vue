<script setup>
defineProps({
    skill: {
        type: Number,
        required: true
    }
})
</script>

<template>
    <div>
        <slot name="title"></slot>
        <slot name="desc"></slot>
        <p>SKILL: {{skill}}pt</p>
    </div>
</template>