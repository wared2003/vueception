<template>
    <div>
        <h2>Counter</h2>
        <div class="flex col-reverse">
            <img @click="count++" class="imgCitrus" src="../assets/logo-active-citrus.svg" alt="">
            <p>{{count}}</p>
            
        </div>
    </div>
</template>

<script>
    export default {
        name : 'CounterVue',
        data() {
            return {
                count: 0,
            }
        }
    }
</script>

<style>
    .flex{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 20px;
    }
    .col-reverse{
        flex-direction: column-reverse;
    }
    .imgCitrus{
        width: 10%;
    }
</style>