<template>
<div class="post">
    <h3>{{post.title}}</h3>
    <p>{{post.content}}</p>
</div>

</template>

<script>
export default {
    name: 'PostItem',
    props:{
        post: Object

    }

}
</script>

<style lang="scss" scoped>

.post{
    padding: 10px 0 10px;
}
</style>
