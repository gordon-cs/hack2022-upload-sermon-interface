<template>
    <div>
        <input class="add" type='text' v-model="this.text" placeholder='Add new tag here'/>
        <button class="add" type="submit" @click="$emit('btn-click', text)">+</button>
    </div>
</template>

<script>
// onsubmit="return tagFormSubmission"
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "tag",
    data() {
        return {
            text: "",
        }
    },
    emits: ['btn-click'],
};
</script>

<style scoped>
    input {
        display: inline-block;
    }
</style>
