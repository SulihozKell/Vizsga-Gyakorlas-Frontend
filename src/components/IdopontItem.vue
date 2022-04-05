<template>
    <div class="col" v-for="idopont in idoponts" v-bind:key="idopont.id">
        <div class="card h-100">
            <img v-if="idopont.tipus == 'szakmai'" src="kutya.png" class="card-img-top" alt="Kutya">
            <img v-if="idopont.tipus == 'erettsegi'" src="macska.png" class="card-img-top" alt="Macska">
            <div class="card-body">
                <h5 class="card-title">{{ idopont.targy }}</h5>
                <p class="card-text">{{ idopont.tipus }}</p>
                <p class="card-text">{{ idopont.kezdes }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'IdopontItem',
    data() {
        return {
            idopont: {
                id: null,
                targy: '',
                tipus: '',
                kezdes: ''
            },
            idoponts: []
        }
    },
    methods: {
        async loadIdoponts() {
            let response = await fetch('http://127.0.0.1:8000/api/idoponts')
            let data = await response.json()
            this.idoponts = data
        }
    },
    mounted() {
        this.loadIdoponts()
    }
}
</script>

<style>
</style>
