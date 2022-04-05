<template>
    <div class="container-fluid">
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
                <div class="navbar-nav">
                    <a class="nav-link" href="#tablazathoz">Táblázat</a>
                    <a class="nav-link" href="#formhoz">Form</a>
                </div>
            </div>
        </nav>
        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3" id="tablazathoz">
            <IdopontItem />
        </div>
        <IdopontForm />
    </div>
</template>

<script>
import IdopontItem from './components/IdopontItem.vue'
import IdopontForm from './components/IdopontForm.vue'
export default {
    name: 'App',
    components: {
        IdopontItem,
        IdopontForm
    }
}
</script>

<style>
</style>
