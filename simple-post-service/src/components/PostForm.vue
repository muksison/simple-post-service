<template>
    <form @submit.prevent>
        <input 
        v-model="post.title"
        class="input" 
        type="text" 
        placeholder="Title"/>

        <input 
        v-model="post.body"
        class="input" 
        type="text" 
        placeholder="Description"/>

        <button 
        class="button"
        @click="createPost">
        Add post
        </button>

    </form>
</template>
<script>
export default {
    data(){
        return {
            post:{
                title:'',
                body:''
            }
        }
    },
    methods:{
        createPost(){
            this.post.id = Date.now();
            this.$emit('createPost', this.post);
            this.post = {
                title:'',
                body:''
            }
        }
    }
}
</script>
<style scoped>
    
.button{
    margin-top:15px;
    align-self: flex-end;
    width: 100%;
    max-width: 100px;
    border: 1px solid green;
    border-radius: 8px;
    padding: 8px;
    color: teal;
    background-color: white;
}

    .button:hover{
        background-color: teal;
        color:white;
        cursor:pointer;
    }

form{
    display: flex;
    flex-direction: column;
}

.input{
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
    border-radius: 8px;

}
</style>