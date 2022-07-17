<template>
<div class="post">
    <h3>
        <router-link :to="{name: 'detail', params: {slug: post.slug} }">{{post.title}}</router-link>
    </h3>
    <i>{{formaDate}}</i>
    <p>{{shortContent}}</p>
</div>

</template>

<script>
import { computed } from 'vue'
export default {
    name: 'PostItem',
    props:{
        post: Object

    },
    computed:{
        shortContent(){
            return this.post.content.substr(0,70) + "...";
        },
        formaDate(){

            const d = new Date(this.post.updated_at);

            let day = d.getDate();
            let month = d.getMonth() + 1;
            const year = d.getFullYear();

            if (day < 10) day = '0' + day;
            if (day < 10) month = '0' + day;

            return `${day}/${month}/${year}`;
        }

    }

}
</script>

<style lang="scss" scoped>

.post{
    padding: 10px 0 10px;
    a{
        color: black;
        text-decoration: none;
        &:hover{
            text-decoration: underline;
        }
    }
}
</style>
