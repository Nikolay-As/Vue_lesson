<template>
<div class="app">

    <form @submit.prevent>
        <h4>Создание поста</h4>
        <input class="input" type="text" placeholder="Название" v-bind:value="title" @input="title = $event.target.value">
        <input class="input" type="text" placeholder="Описание" v-bind:value="body" @input="body = $event.target.value">
        <button @click="AddPost" class="btn" type="submit">Добавить</button>
    </form>

    <div class="post" v-for="post in posts">
        <div>
            <strong>Название:</strong> {{post.title}}
        </div>
    </div>

</div>
</template>

<script>
export default {
    data() {
        return {

            posts: [{
                    id: 1,
                    title: "JavaScript",
                    body: "Описание поста"
                },
                {
                    id: 2,
                    title: "JavaScript",
                    body: "Описание поста"
                },
                {
                    id: 3,
                    title: "JavaScript",
                    body: "Описание поста"
                },
            ],
            title: '',
            body: '',
        }
    },
    methods: {
        AddPost(){
            const newPost = {
                id:Date.now(),
                title: this.title,
                body: this.body,
            }
            this.posts.push(newPost)
            this.title = "";
            this.body = "";
        }


    },
}
</script>

<style>
.post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}

.input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px
}

.app {
    padding: 20px;
}

form {
    display: flex;
    flex-direction: column;

}

.btn {
    align-self: flex-end;
    margin-top: 15px;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal;
}
</style>
