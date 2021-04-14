<template>
    <div class="articles">
        <Title text="Articles" />
        <h4>Params: {{ $route.params.id }}</h4>
    </div>
</template>

<script>
import Title from '../components/Title.vue'

export default {
  components: { 
      Title 
      },
}
</script>
