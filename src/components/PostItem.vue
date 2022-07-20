<template>
    <div class="post">
        <div><strong>Название: </strong>{{ post.title }}</div>
        <div><strong>Описание: </strong>{{ post.body }}</div>
        <div class = "post_btns">
            <default-button>Удалить</default-button>
        </div>
    </div>
</template>

<script>

import DefaultButton from './UI/DefaultButton.vue'

export default {
    props: {
        post: {
            type: Object,
            required: true
        }
    },
    components: { DefaultButton }
}
</script>

<style>

.post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>