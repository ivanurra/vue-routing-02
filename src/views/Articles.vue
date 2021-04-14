<template>
    <div class="articles">
        <Title text="Articles" />
        <hr/>
        <br/>
        <button class="btn" @click="fetchApi">Fetch API</button>
    </div>
</template>

<script>
import Title from '../components/Title.vue'

export default {
    components: { 
        Title 
    },
    data() {
        return {
            arrayBlog: []
        }
    },
    methods: {
        async fetchApi() {
            try {
                const data = await fetch(`https://jsonplaceholder.typicode.com/posts`)
                const array = await data.json()
                console.log(array)
            } catch (error) {
                console.log(error)
            }
        }
    }
}
</script>

<style scoped>
.btn {
    width: 90px;
    background-color: rgb(10, 69, 233);
    color: white;
}
</style>
