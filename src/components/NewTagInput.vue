<template>
    <input 
        type="text" 
        v-model="tag"
        @keydown.enter="newTag"
        @keydown.delete="deleteTag"
    />
</template>

<script lang="ts">
export default {
    name: "NewTagInput",
    emits: ["newTag", "deleteLastTag"],
    data:() => {
        return {
            tag: "",
        }
    },
    methods: {
        newTag(){
            if(this.tag !== "") {
                this.$emit("newTag", this.tag);
                this.tag = "";
            }
        },
        deleteTag(){
            if(this.tag === ""){
                this.$emit("deleteLastTag");
            };
        },
    }
}
</script>

<style>
    input {
        width: max-content;
    }
</style>