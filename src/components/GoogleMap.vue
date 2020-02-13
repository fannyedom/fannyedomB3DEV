<template>
    <div class=" mt-4">
        <br>
        <input type="text" v-model="keyword" v-on:keyup.enter="searchNearBy" class="form-control premierinput">
        <br>

    </div>
</template>

<script>
    export default {
        name: 'GoogleMap',

    }
</script>
