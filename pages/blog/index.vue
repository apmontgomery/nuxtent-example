<template>
  <section class="container">
    <router-link to="/">Home</router-link> / 
    Blog
        <h1>Blog posts</h1>
        <ul>
            <li v-for="post in posts" :key="post.permalink">
                <router-link :to="post.permalink">{{ post.linktitle }}</router-link>
            </li>
        </ul>
  </section>
</template>

<script>

export default {
    asyncData: async function ({ app, route }) {
        var foo =  await app.$content('/').getAll();
        return { posts: foo }
    }
}
</script>
