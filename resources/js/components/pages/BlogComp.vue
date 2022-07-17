<template>
  <div>
    <h1>Blog - I miei post</h1>

    <div>
        <PostItem
        v-for="post in posts"
        :key="post.id"
        :post="post"
        />
    </div>

  </div>
</template>

<script>
import PostItem from "../PostItem.vue";
import { apiUrl } from "../data/config";

export default {
    name: "BlogComp",
    components:{
        PostItem
    },
    data() {
        return {
            apiUrl,
            posts: null
        };
    },
    mounted() {
        this.getApi();
    },
    methods: {
        getApi() {
            axios.get(this.apiUrl)
                .then(res => {
                this.posts = res.data;
                console.log(this.posts);
            });
        }
    },
    components: { PostItem }
}

</script>

<style>

</style>
