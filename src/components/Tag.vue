<template>
    <div>{{ tag.label }} <button class="remove" @click="$emit('btn-click', tag)">x</button></div>
</template>

<script>

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "tag",
    props: {
        tag: Object,
    },
    emits: ['btn-click']
};
</script>

<style scoped>
div {
    font-weight: bold;
    text-align: center;
    display: inline-block;
    margin: 10px;
    padding: 5px;
    border-color: black;
    border-width: 2px;
    border-radius: 20px;
    border-style: dotted;
}
</style>
