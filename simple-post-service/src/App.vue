<template>
    <div class="app">

        <post-form 
        @createPost="addPost" />

        <post-list 
        :posts="posts"/>
    
    </div>
</template>

<script>

import PostForm from './components/PostForm.vue';

import PostList from './components/PostList.vue';

export default {
    components:{
        PostForm,
        PostList
    },
    data(){
        return {
            posts:[
                {id:1, title:'Javascript', body: 'Описание поста 1'},
                {id:2, title:'C#', body: 'Описание поста 2'},
                {id:3, title:'NodeJs', body: 'Описание поста 3'}
            ]
        }
    },
    methods:{
        addPost(post){
            this.posts.push(post);
        }
    }
}
</script>


<style>
*{
    margin:0;
    padding: 0;
    box-sizing: border-box;
}

.app{
    padding: 10px;
    /* display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    max-width: 1920px; */
}

</style>