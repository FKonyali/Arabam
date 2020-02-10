<template>
    <div class="box-container">
        <div class="box" :class="{'is-featured' : item.isFeatured == true}" v-for="item in newItems" :key="item.id">
            <router-link :to="item.id.toString()" :title="item.title" class="box__inner">
                <figure class="box__img">
                    <img :src="item.image" :alt="item.title">
                </figure>
                <div class="box__bar">
                    <h1 v-if="item.isFeatured == true" class="box__btitle">{{item.title}}</h1>
                    <h5 v-if="item.isFeatured == false" class="box__btitle">{{item.title}}</h5>
                    <p class="box__desc">
                        {{item.snippet}}
                    </p>
                </div>
            </router-link>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Content',
  props: ['newItems'],
}
</script>

<style lang="sass">
    h1
        font-size: 34px

    h2
        font-size: 30px

    h3
        font-size: 26px

    h4
        font-size: 22px

    h5
        font-size: 18px
    
    h6
        font-size: 14px

    h1, h2, h3, h4, h5, h6
        font-weight: 700
        margin-bottom: 15px

    .box-container
        display: flex
        flex-wrap: wrap
        margin: 0 -15px

    .box
        position: relative
        width: 33.333%
        padding: 15px 15px

        &.is-featured
            width: 100%

        &__inner
            display: flex
            flex-direction: column
            height: 100%

        &__img
            width: 100%

            img
                width: 100%

        &__bar
            background: #333
            color: #FFF
            padding: 20px
            height: 100%

        &__btitle
            margin-bottom: 15px

        &__desc
            font-size: 12px
            line-height: 18px

    @media (max-width: 630px)
        .box
            width: 100%
</style>
