<template>
  <div class="container">
    <ContentDetail :newItem="newsItem"/>
  </div>
</template>

<script>
import ContentDetail from '@/components/ContentDetail.vue'

export default {
  name: 'Home',
  components: {
    ContentDetail
  },
  data() {
    return {
        newsItem: ''
    }
  },
  created() {
    const newsId = this.$route.params.id;

    fetch('http://sandbox.arabamd.com/news/'+newsId)
    .then(data => data.json())
    .then(json => {
        console.log(json);
        this.newsItem = json;
    });
  }
}
</script>

<style lang="sass">
  .container
    width: 860px
    margin: 30px auto
    max-width: 100%
    padding: 0 30px
</style>