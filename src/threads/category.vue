<template>
    <b-card class="category" v-bind:header="header">
        <b-container>
            <thread v-for="url in sorted"
                :key="url" :properties="threads[url]" :url="url"></thread>
        </b-container>
    </b-card>
</template>

<script>
import thread from './thread.vue';

export default {
    name: 'category',
    components: {
        thread: thread
    },
    props: {
        header: String,
        threads: Object,
        sorted: Array
    }
}
</script>

<style>

.category .card-body {
    padding-left: 0.2em;
    padding-right: 0.2em;
}

.category .thread:first-child {
    margin-top: -0.25em;
}
.category .thread:last-child {
    margin-bottom: -0.25em;
}
.category .thread:not(:last-child) {
    border-bottom: 1px solid rgba(0,0,0,.125);
}
</style>