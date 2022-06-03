<template>
    <div class="posts" v-for="post in posts" :key="post.id">
        <div><strong>Title: </strong>{{post.title}}</div>
        <div><strong>Description: </strong>{{post.body}}</div>
    </div>
</template>
<script>
export default {
    props:{
        posts:{
            type:Array,
            required: true
        }
    }
}
</script>
<style scoped>
.posts{
    padding:15px;
    border: 2px solid teal;
    margin-top: 15px;
    border-radius: 8px;
}
</style>