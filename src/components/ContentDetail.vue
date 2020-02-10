<template>
    <article class="article">
        <router-link to="/" title="Ana Sayfa" class="box__inner"> <span class="article__back">{{homeBackText}}</span> </router-link>
        <figure class="article__img">
            <img :src="newItem.image" :alt="newItem.title">
        </figure>
        <h1>{{newItem.title}}</h1>
        <div class="article__content" v-html="newItem.body">{{newItem.body}}</div>
    </article>
</template>

<script>
export default {
  name: 'ContentDetail',
  props: ['newItem'],
  data() {
    return {
        homeBackText: '< Ana Sayfaya Dön'
    }
  },
}
</script>

<style lang="sass">
    .article
        &__img
            margin-bottom: 15px

            img
                width: 100%

        &__content
            p
                margin-bottom: 15px

        &__back
            margin-bottom: 10px
            color: #333
            text-decoration: underline
</style>
