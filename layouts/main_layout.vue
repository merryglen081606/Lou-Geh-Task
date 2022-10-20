<template>
<div class="page__layout">
    <div class="page__header">
        <Header/>
    </div>
    <div class="page__body">
        <Nuxt />
    </div>
</div>
</template>

<script>
import Header from "../components/header.vue";
import Notes from "../components/notes.vue";

export default {
    components: {
        Header,
        Notes
    }
}
</script>

<style>

</style>