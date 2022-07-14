<template>

<div>
    <HeaderComp/>

    <main>

        <router-view></router-view>

    </main>


    <FooterComp/>
</div>

</template>

<script>

import HeaderComp from './components/HeaderComp.vue';
import FooterComp from './components/FooterComp.vue';


export default {
    name: "App",
    components:{
        HeaderComp,
        FooterComp
    },
    data() {
        return {
            // apiUrl: "http://127.0.0.1:8000/api/posts",
            // posts: null
        };
    },
    methods: {
        // getApi() {
        //     // console.log('API');
        //     // console.log(axios);
        //     axios.get(this.apiUrl)
        //         .then(res => {
        //         this.posts = res.data;
        //         console.log(this.posts);
        //     });
        // }
    },
    mounted() {
        // this.getApi();
    },

}
</script>

<style>


</style>
