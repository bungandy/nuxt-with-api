<template>
  <div class="w-screen h-screen flex justify-center">
    <div class="w-full max-w-screen-sm grid grid-cols-3">
      <div v-for="(i, key) in posts" :key="key" class="flex items-center justify-center rounded m-2 p-5 bg-gray-5 border border-gray-100 hover:bg-gray-100 transform transition hover:-translate-y-1">
        {{i}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return{
      posts: []
    }
  },
  async fetch() {
    // this.posts = await this.$http.$get('/api/filterPosts')
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then(response => {
        response.json()
        console.log(response)
      })
      .then(data => {
        console.log(data)
        this.posts = data
      })
    // console.log(this.posts)
  }
}
</script>
