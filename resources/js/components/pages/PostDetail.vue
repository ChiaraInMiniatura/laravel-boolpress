<template>
  <div class="container">
    <h1>PostDatail - Dettagli Post</h1>
    <h3>{{post.title}}</h3>
    <h3>{{post.category.name}}</h3>
    <div>
        <span class="tag" v-for="tag in post.tags" :key="tag.id">
            {{tag.name}}
        </span>
    </div>

    <p>{{post.content}}</p>


  </div>
</template>

<script>
import Axios from 'axios';
import { apiUrl } from '../data/config';

export default {
    name:'PostDetail',
    data(){
        return{
            post:{
                title:'',
                content:'',
                category:'',
                tags:[],
            },
            apiUrl,
        }
    },
    mounted(){
        this.getApi()
    },
    methods:{
        getApi(){
            console.log(this.$route.params.slug);
            Axios.get(this.apiUrl + '/' + this.$route.params.slug)
            .then(res => {
                console.log(res.data);
                this.post = res.data;
            })
        }
    }


}
</script>

<style lang="scss" scoped>
h1,h3,p{
    padding: 10px 0;
}
.tag{
    background-color: rgba(44, 127, 236, 0.438);
    padding: 5px 7px;
    border-radius: 2px;
    margin: 10px 5px 10px 0;
}

</style>
