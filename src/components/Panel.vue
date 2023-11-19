<template>
    <h1>Introduce your tags</h1>
    <div id="tagsAndInput">
        <span v-for="(tag, index) in tagsArray" :key="index"> 
            <Tag :tag="tag" @deleteTag="deleteTag($event)"/>
        </span>
        <NewTagInput 
            @newTag="saveTag($event)" 
            @deleteLastTag="deleteLastTag"
        />
    </div>
</template>

<script lang="ts">
import NewTagInput from './NewTagInput.vue';
import Tag from './Tag.vue';

export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "Panel",
    components:{
        NewTagInput,
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

<style scoped>
    h1 {
        margin: 0 auto;
        color: aliceblue;
        text-align: center;
        text-transform: uppercase;
        padding-bottom: 30px;
    }

    #tagsAndInput {
        display: block;
        background-color: white;
        padding: 15px 10px;
        margin: auto;
    }
</style>>