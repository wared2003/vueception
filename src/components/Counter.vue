<template>
    <div>
        <h2>Counter</h2>
        <div class="flex">
            <button @click="count--">-</button>
            
            <p>{{count}}</p>
            
            <button @click="count++">+</button>
            
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
</style>