<template>
    <div class="cards">
        <citycards 
            v-for="(city, i) in citydata"
            :id = citydata[i].id
            :cityData = citydata
        />
    </div>
</template>

<style scoped>
.cards{
    margin-left: 10px;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
}
</style>


<script>
import citycards from './citycards.vue';
export default{
    name : 'cityscardslist',
    components: {
        citycards
    },
    props : ['citydata']
}

</script>