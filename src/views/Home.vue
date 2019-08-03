<template>
  <div class="home-container">
    <!-- <HelloWorld msg="Kuch bhi dhundho"/> -->
    <b-row>
      <b-col>
        <b-form-input
          id="search-input"
          type="text"
          v-model="searchQuery"
          required
          placeholder="Search product"
        ></b-form-input>
      </b-col>
      <b-col>
        <b-button variant="success" id="search-button" @click="searchCall()">Search</b-button>
      </b-col>
    </b-row>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  // components: {
  //   HelloWorld
  // }
  data () {
    return {
      searchQuery: ""
    }
  },
  methods: {
    searchCall: function () {
      this.$store.dispatch('search', this.searchQuery)
    }
  },  
}
</script>

<style lang="scss">
  #search-input {
    width: 122%;
    margin-left: 20%;
    height: 50px;
    font-size: 20px;
    background: url(https://img.icons8.com/color/48/000000/search.png) no-repeat;
    background-position: 98%;
    background-size: 4%;
  }
  .home-container {
    margin: 2% 10%;
  }
  #search-button {
    margin-left: 2%;
    width: 30%;
    height: 50px;
    font-size: 20px;
  }
</style>
