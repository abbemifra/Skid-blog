<template>
    <div class="min-h-screen bg-coolgray" >
        <div class="mx-auto w-1/2 bg-white p-5 rounded-xl">
            <h1 class="text-5xl mb-8 text-center font-serif">{{ article.title }}</h1>
            <img :src="article.image" class="obejct-cover    "/>
            <p class="mb-8">{{ article.description }}</p>
            <nuxt-content :document="article"></nuxt-content>
        </div>
    </div>
</template>

<script>
export default {
    async asyncData({ $content, params }) {

        let article = await $content('Articles/article' + params.id).fetch()
        console.log(article)

        return {
            article
        }
    },
}
</script>