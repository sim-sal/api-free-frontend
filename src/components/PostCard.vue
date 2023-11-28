<script>
export default {
    name: 'PostCard',
    props: {
        post: {
            type: Object,
            required: true
        }
    }
}
</script>

<template>
    <div class="col-4 my-3 text-center">
        <div class="card">
            <img class="card-img-top" :src="post.image" alt="Card image cap">
            <div class="card-body">
                <div class="card-title">
                    <h2>{{ post.title }}</h2>
                </div>
                <p>{{ post.content }}</p>
                <p v-if="post.category"><strong>Category:</strong> {{ post.category.name }}</p>
                <p v-if="post.tags.length > 0"><strong>Tags:</strong></p>
                <ul v-if="post.tags.length > 0">
                    <li v-for="(tag, index) in post.tags" :key="index">{{ tag.name }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style>
.card {
    background-color: rgb(218, 218, 218);
}

.card-title {
    background-color: white;
}
</style>