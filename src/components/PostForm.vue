<template>
    <form @submit.prevent>
        <h4>Создание поста</h4>
        <input v-model="post.title" class="input" type="text" placeholder="Название">
        <input v-model="post.body" class="input" type="text" placeholder="Описание">
        <default-button  @click="createPost">Создать</default-button>
    </form>
</template>

<script>
import DefaultButton from './UI/DefaultButton'
export default {
    data() {
        return {
            post: {
                title: "",
                body: ""
            }
        };
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit("create", this.post);
            this.post = {
                title: "",
                body: ""
            };
        }
    },
    components: { DefaultButton }
}
</script>

<style>
form {
    display: flex;
    flex-direction: column;
}
</style>