<template>
    <div>
            <h1>Participants list</h1>
            <ol>
                <li v-for="person in list">
                    {{ person.firstname }}
                    {{ person.lastname }}
                </li>
            </ol>
    </div>
</template>

<script>
    export default {
        props: ['list']
    };
</script>

<style>
    ol{
        color:deeppink;
    }
</style>