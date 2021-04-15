<template>
<Title text="Params Route" />
<h3>Params: {{ $route.params.id }}</h3>
</template>

<script>
import Title from '../components/Title.vue'
export default {
    components: { 
        Title 
    },
}
</script>
