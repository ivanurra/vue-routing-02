<template>
<Title text="Params Route" />
<h3>Params: {{ $route.params.id }}</h3>
<h3>{{ article.title }}</h3>
<p>{{ article.body }}</p>
</template>

<script>
import Title from '../components/Title.vue'
export default {
    components: { 
        Title 
    },
    data() {
        return {
            article: {}
        }
    },
    methods: {
        async fetchApi() {
            try {
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`)
                const array = await data.json()
                console.log(array)
                this.article = array
            } catch (error) {
                console.log(error)
            }
        }
    },
    created() {
        this.fetchApi();
    }
}
</script>
