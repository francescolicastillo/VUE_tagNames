<template>
  <span>{{tag}}</span>
  <button @click="deleteTag(tag)">X</button>
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

</style>