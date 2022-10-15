<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="header">How would you describe your sermon?</div>
    <button class="submit" @click="$emit('btn-click', tagList)">Submit</button>
    <div class="tagContainer">
        <div class="h5">
            tags
        </div>
        <AddTag @btn-click="addTag"/>
        <div class="list" v-for="tag in tagList" :key="tag.id">
           <Tag @btn-click="removeTag" :tag="tag"/>
        </div>
    </div>
</template>

<script>
import Tag from './Tag.vue'
import AddTag from './AddTag.vue'

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Tags',
    components: {
        // eslint-disable-next-line vue/no-unused-components
        Tag,
        AddTag,
    },
    data() {
        return {
            tagList: [
                // {id: int, label: String}
            ],
            id: 0,
        }
    },
    emits: ['btn-click'],
    methods: {
        removeTag(tag) {
            console.log("removed: ", tag);
            this.tagList.splice(this.tagList.indexOf(tag), 1);
        },
        addTag(newLabel) {
            if (newLabel) {

                let id = this.id;

                if (this.tagList.findIndex(e => e.label == newLabel) > -1) {
                    alert("This tag already existed.");
                }
                else {
                    let newTag = {id: id, label: newLabel};
                    console.log("Added: ", newTag);

                    this.tagList.push(newTag);
                    this.id++;
                }
            }
            else {
                alert("The input cannot be empty.");
            }
        }
    }
}

</script>

<style scoped>
    div.tagContainer {
        min-height: 200px;
        margin: 0 200px;
        border-color: black;
        border-width: 2px 0 0 0;
        border-style: solid;
    }
    div.list {
        display: inline-block;
    }
</style>