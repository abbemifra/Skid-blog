<template>
<div class="bg-white rounded-xl pb-2 transform hover:scale-105 ease-in-out duration-500 cursor-pointer mt-52" >
    <h3  class="text-3xl pb-2 pl-2 font-serif font-medium text-center" >{{item.title}}</h3>
    <img :src="item.image" alt="article image" class="h-44 w-full object-cover " >
    <p class="pl-2 text-center">{{item.description}}</p>
</div>
</template>

<script>
export default {
    props:['item'],
    data() {
        return {

        }
    }
}
</script>