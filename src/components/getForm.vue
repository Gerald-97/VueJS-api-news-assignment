<template>
    <div>
        <div v-for="(news, index) in newsList" :key="index">
            <div class="news__card">
                <div class="card__item image__wrapper">
                    <img :src="news.urlToImage" alt="News Image" class="newsImage">
                </div>
                <div class="card__item news__title">
                    <h2>{{news.title}}</h2>
                    <h5>{{news.author}}</h5>
                </div>
                <div class="card__item news__page">
                    <h4>{{news.description}}</h4>
                    <p>{{news.content}}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'getForm',
    data(){
        return {
            newsList: []
        }
    },
    mounted(){
        this.$http.get('https://newsapi.org/v2/top-headlines?country=us&apiKey=b7fa48e370cc4303824eb19e3a4e19d0')
        .then(response => {
            this.newsList = response.data.articles
        })
        .catch(error => {
            alert(error)
        })
    }
}
</script>
<style scoped>
.news__card{
    padding-left: 10rem;
    /* height: 20rem; */
    border-bottom: 2px solid black;
    display: block;
    background-color: beige;
    margin-bottom: 5px;
}
.image__wrapper{
    width: 80%;
    /* height: 10rem; */
}
.newsImage{
    width: 100%;
    /* max-height: 10rem; */
    overflow: hidden;
}
.news__title{
    text-align: right;
    border-bottom: 1px solid gray;
}
.news__page{
}
</style>