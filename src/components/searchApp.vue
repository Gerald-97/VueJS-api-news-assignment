<template>
    <div class="container">
        <div class="searchBar">
            <label for="searchBar">Search</label>
            <input type="text" name="search" id="" v-model="keyWord">
            <button @click="filterGallery">Filter</button>
        </div>
        <div class="gallery">
            <div class="gallery__item" v-for="card in galleryCards" :key="card.Name">
              <h3>{{card.Name}}</h3>
              <img :src="card.Url" :alt="hero" :class="gallery__image">
              <h4>{{card.Type}}</h4>
              <button @click="deleteKey(index)">Delete Entry</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  name: 'SearchApp',
  data(){
        return{
          keyWord: '',
          hero:"Profile Image",
          galleryCards:[
        {
          Name: "John Frusciante",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/152457.jpg"
        },
        {
          Name: "Reservoir Dogs",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151257.jpg"
        },
        {
          Name: "Foo Fighters",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151557.jpg"
        },
        {
          Name: "Pearl Jam",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Sublime",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Inglourious Basterds",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Incubus",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Audioslave",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Jackie Brown",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Nirvana",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "The Big Lebowski",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Goodfellas",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Guns N' Roses",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Death Proof",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "The Offspring",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Django Unchained",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Rage Against The Machine",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Snatch",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Trainspotting",
          Type: "movie",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        },
        {
          Name: "Weezer",
          Type: "music",
          Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
        }
        ]

      }
  },
  methods:{
    deleteKey(index){
      this.galleryCards.splice(index, 1);
    }
  },
  computed:{
    }
  }
</script>
<style scoped>
  .gallery{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    margin: 10px;
    width: 80%;
    border: 2px solid black;
    border-radius: 15px;
  }
  .gallery__item{
    margin: 5px;
    border: 1px dotted rgb(34, 32, 32);
    border-radius: 10px;
  }
  .gallery__item > h4{
    margin: 6px;
  }
  .gallery__item > h3{
    margin: 10px;
  }
  .gallery__item > img{
    width: 90%;
  }
  button{
    margin-bottom: 5px;
  }
</style>