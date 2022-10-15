<template>
    <div>
        <input
            class="add"
            ref="tag"
            type="text"
            v-model="this.text"
            @keypress.enter="pressAdd"
            placeholder="Add new tag here"
        />
        <button
            class="add"
            type="submit"
            @click="pressAdd"
        >
            +
        </button>
    </div>
</template>

<script>

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "tag",
    data() {
        return {
            text: "",
        };
    },
    emits: ["btn-click"],
    methods: {
        pressAdd() {
            this.$emit('btn-click', this.text.toUpperCase().trim());
            this.clearInput();
            this.focusInput();
        },
        clearInput() {
            this.text = "";
        },
        focusInput() {
            this.$nextTick(() => this.$refs["tag"].focus())
        },
    }
};
</script>

<style scoped>
input {
    display: inline-block;
}
</style>
