                                                                                                                                                                                <template>
  <div class="container" v-if="this.$store.state.user.displayName">
    <h4>Welcome {{this.$store.state.user.displayName}}! What's happening?</h4>
    <br>
    <div class="form-group">
      <input type="text" class="form-control" id="title" placeholder="Title" v-model="title">
    </div>
    <div class="form-group">
      <textarea class="form-control" id="body" rows="5" placeholder="Write your thoughts here..." v-model="body">
      </textarea>
    </div>
    <button class="btn btn-primary" @click="addPost()">Post</button>
    <hr>
  </div>
  <div class="container" v-else>
    <h3>Login to access Toro Net</h3>
    
    <div >
    <a href="/login"><img src="https://i.imgur.com/bGlcYmy.png"/></a> 
    </div>

    <!--<img src="https://i.imgur.com/ytdAxfF.png">-->                                                                                                
    <!--<img src="src/components/assets/ToroNet.png">-->
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {                                    
    return {
      title: '',
      body: ''
    };
  },
  methods: {
    addPost() {
      this.$store.dispatch('addPost', this.$store.state.posts)
    }
  },
  mounted() {
    this.$store.dispatch('getPosts')
    this.$store.dispatch('getUser')
  },
}
</script>
