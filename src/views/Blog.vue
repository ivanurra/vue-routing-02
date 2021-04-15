<template>
    <div class="articles">
        <Title text="Articles" />
        <hr/>
        <br/>
        <!-- <button class="btn" @click="fetchApi">Fetch API</button> -->
        <div class="titles" v-for="item in arrayBlog" :key="item.id">
            <router-link :to="`/blog/${item.id}`">
                {{item.id}} - {{ item.title }}
            </router-link>
        </div>
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
                this.arrayBlog = array;
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

<style scoped>
.btn {
    width: 90px;
    background-color: rgb(10, 69, 233);
    color: white;
}
.titles {
    display: flex;
    align-items: flex-start;
    margin-top: 6px;
}
</style>
