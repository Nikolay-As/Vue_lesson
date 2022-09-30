<template>
    <div>
       <div>Кол-во лайков <strong>{{likes}}</strong></div>
        <div>Кол-во дизлайков <strong>{{dislikes}}</strong></div>

       <div>
        <button type="submit" v-on:click="addLikes" >Лайк</button>
        <button type="submit" @click = "addDislikes" >Дизлайк</button>
       </div> 
    </div>
</template>

<script>
export default {
    data(){
        return {
            likes: 0,
            dislikes: 0,
        }
    },
    methods: {
        addLikes(){
            this.likes += 1;
        },
        addDislikes(){
            this.dislikes += 1;
        }
    },
}
</script>


<style>

</style>