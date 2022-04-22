<template>

  <div class=" mountain  flex flex-wrap justify-center        ">
    <div @click="goToarticle(article.id)" class="w-80 m-4" v-for="article in Articles" :key="article.id">
      <TripListItem :item="article"></TripListItem>
    </div>
  </div>

    </template>

    <script>
    export default {
  async asyncData({$content}) {
    let Articles = await $content('Articles').sortBy('id', 'desc').without(['body']).fetch()
    return {
      Articles
    }
  },
  methods: {
    goToarticle(id) {
      this.$router.push('/trip-details/'+id)
            }
        }
    }

</script>

<style>

.mountain {
    background-image: url("https://wallpaperaccess.com/full/882671.jpg");
   
   background-position: center;
   
   background-repeat: no-repeat;
   
   background-size: cover;
   
   height: 100vh;
}

</style>