<script setup lang="ts">
const props = defineProps({
    name: { type: String, required: true },
    desc: { type: String, required: true },
    href: { type: String, required: true },
})
</script>

<template>
    <div style="width:95%">
        <h2>{{ props.name }}</h2>
        <p>{{ props.desc }}</p>
        <mdui-button :href="props.href" end-icon="arrow_forward" style="font-family: sans-serif;">Go</mdui-button>
    </div>
</template>