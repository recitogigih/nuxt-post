<template>
  <div>
    <navbar />

    <div class="blogs-page">
      <div class="main-content">
        <div class="container">
          <div class="columns is-mobile">
            <div class="column is-8 is-offset-2">
              <div class="section">
                <div class="title">
                  <h1>Newest Posts</h1>
                  <hr>
                </div>

                <post-item v-for="post in posts" 
                  :key="post._id" 
                  :title="post.title" 
                  :subtitle="post.subtitle" 
                  :date="post.createdAt" 
                  :isRead="post.isRead"
                />

              </div>
              <!-- end of post -->
            </div>
            <!-- end of side bar -->
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Navbar from '~/components/Navbar'
  import PostItem from '~/components/PostItem'
  export default {
    components: {
      Navbar,
      PostItem
    },
    data() {
      return {
        posts: [{
            _id: 1,
            title: 'My 1 post',
            subtitle: 'My 1 subtitle',
            createdAt: new Date(),
            isRead: false
          },
          {
            _id: 2,
            title: 'My 2 post',
            subtitle: 'My 2m  subtitle',
            createdAt: new Date(),
            isRead : true
          },
        ]
      }
    }
  }

</script>
