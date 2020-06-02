<template>
    <div id="app-articles" class="container">
        <div class="row">
            <div class="col-sm-6">
                <h2 class="text-center">Articles</h2>
                <div class="article row" v-for="article in limitArticles" :key="article.id">
                    <div class="img-circle">
                        <img src="../assets/author.png" class="author" />
                    </div>
                    <div class="col-md-5 col-sm-6">
                    <h4 class="article-title no-margin">{{article.title}}</h4>
                    <p class="article-info">
                        <span class="font-gray">Friday December 16, 2019</span><br/>
                        <span class="font-blue-violet">Fred The Slasher Designer</span>
                    </p></div>
                    <p class="article-body">
                        {{article.body}}
                    </p>
                        <a class="article-more" href="#">Read more</a>
                </div>
                <p class="text-center">
                    <span class="link" @click="limit=false" v-if="limit">Explore more articles</span>
                    <span class="link" @click="limit=3" v-else>Show Less</span>
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['articles'],
    name: 'app-articles',
    data() {
        return {
            limit: 3
        }
    },
    computed: {
        limitArticles() {
            return this.limit ? this.articles.slice(0, this.limit) : this.articles
        }
    }
}
</script>