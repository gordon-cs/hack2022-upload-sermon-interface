<template>
    <div class="canvas">
        <header>
            <div class="title">{{ title }}</div>
        </header>
        <!-- <div class="title">Upload your sermons</div> -->
        <!-- <div class="header">How would you describe your sermon?</div>
        <button class="submit" @click="sumbitTags">Submit</button> -->
        <Tags @btn-click="submitTags"/>
    </div>
</template>

<script>
import Tags from './Tags.vue'

export default {
    name: "NewComponent",
    props: {
        title: String,
    },
    components: {
        Tags,
    },
    data() {
        return {
        }
    },
    methods: {
        submitTags(tags) {
            let tagList = JSON.parse(JSON.stringify(tags));
            console.log(tagList);
        }
    }
};
</script>

<style>
div {
    font-family: "Courier New", Courier, monospace;
}
div.canvas {
    margin: 0 100px;
}
div.title {
    font-size: 60px;
    margin: 50px 350px;
}
div.header {
    font-size: 30px;
    display: inline;
}
div.h5 {
    font-size: 20px;
}
button {
    font-family: "Courier New", Courier, monospace;
}
button.submit {
    background-color: #4caf50; /* Green */
    border-radius: 20px;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 30px;
    margin: 20px;
}
button.submit:hover {
    color: #4caf50; /* Green */
    background-color: white;
    border-color: #4caf50;
}
button.remove {
    background-color: white;
    color: grey;
    padding: 2px;
    text-align: center;
    display: inline-block;
    border-width: 0;
    font-size: 20px;
}
button.remove:hover {
    color: red;
}
button.add {
    width: 38px;
    font-size: 20px;
    font-weight: bold;
    text-align: center;
    display: inline-block;
    margin: 10px;
    padding: 5px;
    border-color: black;
    border-width: 2px;
    border-radius: 30px;
    border-style: solid;
    color: white;
    background-color: #4caf50;
}
button.add:hover {
    color: #4caf50; /* Green */
    background-color: white;
    border-color: #4caf50;
}
input {
    font-family: "Courier New", Courier, monospace;
}
input.add {
    font-size: 18px;
    font-weight: bold;
    display: inline-block;
    margin: 5px;
    padding: 5px;
    border-color: black;
    border-width: 2px;
    border-radius: 30px;
    border-style: solid;
}
input.add::placeholder {
    font-style: italic;
}
</style>
