<template>
  <div class="container">
    <ContentBox :newItems="news"/>
  </div>
</template>

<script>
import ContentBox from '@/components/ContentBox.vue'

export default {
  name: 'Home',
  components: {
    ContentBox
  },
  data() {
    return {
        news: ''
    }
  },
  created() {
    fetch('http://sandbox.arabamd.com/news')
    .then(data => data.json())
    .then(json => {
        this.news = json;
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