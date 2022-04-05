<template>
    <div class="mb-3">
        <label for="idoponttargy" class="form-label">Tárgy</label>
        <input v-model="idopont.targy" type="text" class="form-control" id="idoponttargy">
    </div>
    <div class="mb-3">
        <label for="idoponttipus" class="form-label">Típus</label>
        <select v-model="idopont.tipus" name="cars" class="form-control" id="idoponttipus">
            <option value="erettsegi">Érettségi</option>
            <option value="szakmai">Szakmai</option>
        </select>
    </div>
    <div class="mb-3">
        <label for="idopontkezdes" class="form-label">Kezdés</label>
        <input v-model="idopont.kezdes" type="date" class="form-control" id="idopontkezdes">
    </div>
    <button @click="newIdopont" class="btn btn-primary" id="formhoz">Új felvétele</button>
</template>

<script>
export default {
    name: 'IdopontForm',
    data() {
        return {
            idopont: {
                id: null,
                targy: '',
                tipus: '',
                kezdes: ''
            }
        }
    },
    methods: {
        async newIdopont() {
            await fetch('http://127.0.0.1:8000/api/idoponts', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Accept': 'application/json'
                },
                body: JSON.stringify(this.idopont) 
            })
        }
    }
}
</script>

<style>
</style>
