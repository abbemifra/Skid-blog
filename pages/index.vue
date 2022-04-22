<template>
  <div>
    <div class="background-image">
      <h1 class=" text-2xl text-left absolute bottom-0 right-0 text-white flex items-end font-bold">

        Made by Emil Frank

      </h1>
    </div>

    <div class="second-background">
      <h1 class="text-center text-white text-xl">

        Latest Post:

      </h1>

      <div class="flex justify-center items-center gap-4">
        <div class="">
          <img :src="blog.image" alt="" class="h-96 w-96 mt-20 ">
        </div>

        <div>
          <h1 class="text-2xl text-white mb-2 font-bold       ">
            {{ blog.title }}
          </h1>

          <p class="text-white font serif"> {{ blog.description }}</p>
          <button class="text-black hover:scale-105 ease-in-out duration-500 p-1 bg-white font-bold font-mono mt-3   "
            @click="goToPost(blog.id)">

            Read more!
          </button>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({ $content }) {
    let newPost = await $content("Articles")

      .without(["body"])

      .sortBy("id", "desc")

      .limit(1)

      .fetch();

    let blog = newPost[0];

    return {

      blog,
    };
  },

  methods: {
    goToPost(id) {
      this.$router.push("/trip-details/" + id);
    },
  },
}

</script>

<style>
.welocme {
  text-align: center;
}

.footer {
  position: sticky;
  height: 50px;
}

.background-image {
  background-image: url("https://i.pinimg.com/originals/cb/d5/50/cbd550d4f42345e536a864def7faff15.jpg");

  background-position: center;

  background-repeat: no-repeat;

  background-size: cover;

  height: 100vh;

}

.second-background {
  background-image: url("https://mir-s3-cdn-cf.behance.net/project_modules/1400/c29fa615880153.56298181d0832.jpg");

  background-position: center;

  background-repeat: no-repeat;
  
  background-size: cover;
  
  height: 100vh;
}
</style>