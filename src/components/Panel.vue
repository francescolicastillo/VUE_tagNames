<template>
    <h1>Introduce your tags</h1>
    <span v-for="(tag, index) in tagsArray" :key="index"> 
        <Tag :tag="tag" @deleteTag="deleteTag($event)"/>
    </span>
    <Input 
        @newTag="saveTag($event)" 
        @deleteLastTag="deleteLastTag"
    />
</template>

<script lang="ts">
import Input from './Input.vue';
import Tag from './Tag.vue';

export default {
    name: "Panel",
    components:{
        Input,
        Tag,
    },
    data:() => {
        return {
            tagsArray: [] as Array<string>,
        }
    },
    methods: {
        saveTag(tagEmit: string) {
            if(!this.tagsArray.some(tag => tag === tagEmit)){
                this.tagsArray.push(tagEmit);
            }
        },
        deleteTag(tagDelete: string) {
            this.tagsArray = Array.from(this.tagsArray).filter(tag => tag !== tagDelete);
        },
        deleteLastTag(){
            this.tagsArray.pop();
        },
    },
}
</script>

<style>

</style>