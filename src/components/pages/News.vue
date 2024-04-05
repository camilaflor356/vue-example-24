<script>
import NewsItem from "../widgets/NewsItem.vue";
import NewsItemFooter from "../widgets/NewsItemFooter.vue";
import TimeStamp from "../widgets/TimeStamp.vue";
import axios from '/node_modules/axios';
export default {
    data() {
        return {
            featuredArticle: {
                imageUrl: "https://images.performgroup.com/di/library/omnisport/79/d8/6c9b4b26f64a40ea89b7f69ccd088d40.jpg?t=-955230179&w=640",
                title: "Inter boss Simone Inzaghi reveals admiration for Diego Simeone ahead of clash",
                gmtTime: "2024-02-19T20:04:27.000Z",
                source: "FotMob",
                lead: "Simone Inzaghi and Diego Simeone, now boss of Atletico Madrid, helped Lazio win Serie A as players in 2000.",
                sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                pageURL: "https://www.fotmob.com/news/138lzxhk8mmsi1nflku3xemdte-inter-boss-simone-inzaghi-reveals-admiration-diego-simeone-ahead-clash"
            },
            articles: [
                {
                    imageUrl: "https://images2.minutemediacdn.com/image/upload/c_crop,w_1566,h_880,x_0,y_36/c_fill,w_2160,ar_16:9,f_auto,q_auto,g_auto/images%2FvoltaxMediaLibrary%2Fmmsport%2F90min_en_international_web%2F01hqqjyccm1peyq227pt.png",
                    title: "INEOS Man Utd didnt consider signing Tino Livramento",
                    gmtTime: "2024-02-28T06:30:00.000Z",
                    source: "FotMob",
                    lead: "New Manchester United shareholders INEOS were surprised the club did not make a play to sign Tino Livramento before his move to Newcastle United last summer, 90min understands.",
                    sourceIconUrl: "https://images2.minutemediacdn.com/image/upload/c_crop,w_1566,h_880,x_0,y_36/c_fill,w_2160,ar_16:9,f_auto,q_auto,g_auto/images%2FvoltaxMediaLibrary%2Fmmsport%2F90min_en_international_web%2F01hqqjyccm1peyq227pt.png",
                    pageURL: "https://www.fotmob.com/embed/news/01hqqjtz8s30/ineos-surprised-man-utd-didnt-consider-signing-tino"
                },
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/5b/98/2_72303704.jpg?t=-193833667&w=1200&h=630",
                    title: "Newcastle United co-owner challenges £36m bankruptcy petition in court",
                    gmtTime: "2024-02-19T12:48:00.000Z",
                    source: "FotMob",
                    lead: "Amanda Staveley asked the Insolvency and Companies Court to set aside a demand served by Victor Restis in May last year.",
                    sourceIconUrl: "https://images.performgroup.com/di/library/omnisport/5b/98/2_72303704.jpg?t=-193833667&w=1200&h=630",
                    pageURL: "https://www.fotmob.com/news/xj9v4rc16un1va0zrsbcdh5z-newcastle-united-co-owner-challenges-36m-bankruptcy-petition-court"
                 },
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/8d/8/2_75440707.jpg?t=-220835411&w=1200&h=630",
                    title: "Pep Guardiola hails 'unbelievable' Erling Haaland goalscoring record",
                    gmtTime: "2024-02-19T12:47:00.000Z",
                    source: "FotMob",
                    lead: "Amanda Staveley asked the Insolvency and Companies Court to set aside a demand served by Victor Restis in May last year.",
                    sourceIconUrl: "https://images.performgroup.com/di/library/omnisport/8d/8/2_75440707.jpg?t=-220835411&w=1200&h=630",
                    pageURL: "https://www.fotmob.com/news/1iutcondqtpkv1py3odlsynnnf-pep-guardiola-hails-unbelievable-erling-haaland-goalscoring-record",
                },
                {
                    imageUrl: "https://latest.fotmob.com/wp-content/uploads/2024/02/Covers_This-Is-Anfield-2802-1.png",
                    title: "Liverpools kids show the future really is bright after Jurgen Klopp",
                    gmtTime: "2024-02-19T03:34:00.000Z",
                    source: "FotMob",
                    lead: "When Jürgen Klopp first arrived at Liverpool he spoke of his intention to use the club’s under-23s side similarly to the way European sides in Germany and Spain have second teams.",
                    sourceIconUrl: "https://latest.fotmob.com/wp-content/uploads/2024/02/Covers_This-Is-Anfield-2802-1.png",
                    pageURL: "https://www.fotmob.com/topnews/10444-liverpools-kids-show-future-really-is-bright-after-jurgen-klopp?utm_source=fotmob"
                },
            ],
        }
    },
    components: {
        NewsItem,
        TimeStamp,
        NewsItemFooter
    },
    methods: {
        functionName() {
            console.log('hi')
        axios.get("https://fotmob-backend.onrender.com/articles").then(response => {
               console.log(response.data); // set articles equal to response.data 
           })
        }
    }
}
</script>


<template>
    <header class="WorldNewsHeader">
        <h1>World News</h1>
        <button @click="functionName"> hi</button>
    </header>
    <div class="layout">
        <div class="featuredArticle">
            <div class="featuredImage">
                <img :src="featuredArticle.imageUrl" alt="featured article image" />
            </div>
            <div class="featuredArticleText">
                <h3>{{ featuredArticle.title }}</h3>
                <NewsItemFooter :article="featuredArticle" />
            </div>
        </div>
        <div class="articleGrid">
            <NewsItem v-for="article in articles" :newsItem="article" :key="article.title" />
        </div>
    </div>
</template>

<style scoped>
.WorldNewsHeader {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    margin: 0px 30px;
}
.featuredArticle {
    cursor: pointer;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: 1fr;
    padding: 0px 30px;
    position: relative;
}
.featuredImage {
    width: 100%;
    height: 100%;
    max-width: 640px;
}
.featuredImage>img {
    /* needs to also specify child to resize */
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.featuredArticleText {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    -webkit-box-pack: center;
    justify-content: center;
    background: var(--GlobalColorScheme-Background-background2);
    height: 100%;
    width: 100%;
    flex-direction: column;
    gap: 24px;
    padding: 20px;
}
.articleGrid {
    margin-top: 48px;
    padding: 0px 30px;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 40px 24px;
    -webkit-box-align: start;
    align-items: start;
}
</style>