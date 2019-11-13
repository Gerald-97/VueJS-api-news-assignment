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
                    <h3>{{news.description}}</h3>
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
    width: 100%;
    height: 10rem;
    border-bottom: 1px solid grey;
    display: block;
}
.image__wrapper{
    justify-content: right;
    width: 80%;
    height: 5rem;
}
.newsImage{
    width: 100%;
    height: inherit;
}
</style>