<template>
    <div>
        <span>{{tag}}</span>
        <button @click="deleteTag(tag)" title="Delete tag">X</button>
    </div>
</template>

<script lang="ts">

export default {
    props: {
        tag: String,
    },
    emits: ["deleteTag"],
    setup(props){
        props.tag
    },
    methods: {
        deleteTag(tag: String) {
            this.$emit('deleteTag', tag)
        }
    }
}
</script>

<style>
    div {
        display: inline;
        background-color: rgb(255, 217, 0);
        margin: 15px 2px;
        padding: 5px 3px;
        border-radius: 5px;
    }

    button {
        border: none;
        background-color: transparent;
        color: brown;
        cursor: pointer;
    }
</style>