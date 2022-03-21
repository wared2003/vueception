<template>
    <div>
        <h2>Counter</h2>
        <div class="flex col-reverse">
          <img @click="count++" class="imgCitrus" src="../assets/logo-active-citrus.svg" alt="clicker logo">
          <p>{{count}}</p>



        </div>
    </div>
  <marquee  class="alexis" v-if="count > 10"><img src="../assets/alexis.png"> </marquee>
  <marquee  class="alexis" v-if="count > 15"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 20"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 25"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 30"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 35"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 40"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 45"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 50"><img src="../assets/alexisBTP.webp"> </marquee>
  <marquee  class="alexis" v-if="count > 55"><img src="../assets/alexisBTP.webp"> </marquee>
</template>

<script>
    export default {
        name : 'CounterVue',
        data() {
            return {
                count: 0,
            }
        },
    }

</script>

<style>
    .flex {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 20px;
    }
    .col-reverse {
      flex-direction: column-reverse;
    }
    .imgCitrus {
      width: 150px;
      cursor: pointer;
      transition: all 0.3s;
    }
    .imgCitrus:hover {
      transform: scale(1.20);
    }
    .imgCitrus:active {
      transform: scale(1.02);
    }
    .alexis{
      display: block;
      width: 75%;
      margin-left: auto;
      margin-right: auto;
    }
</style>