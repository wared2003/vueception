<template>
  <div>
    <nav>
      <ul>
        <li @click="changeActive(tab.slug)" :class="{active: tab.active}" v-for="tab in tabulation" :key="tab.slug">{{tab.title}}</li>
      </ul>
    </nav>
    <div>
      <CounterVue v-if="activePage == 'counter'" />
      <FormVue v-if="activePage == 'form'" />
      <SettingsVue v-if="activePage == 'settings'" />
    </div>
  </div>
</template>

<script>

import CounterVue from "./components/Counter.vue";
import FormVue from './components/Form.vue';
import SettingsVue from './components/Settings.vue';
export default {
  name: 'App',
  components: {
    CounterVue,
    FormVue,
    SettingsVue,
},
  data(){
    return{
      tabulation: [
        {
          slug: 'counter',
          title: 'Counter',
          active: true,
        },
        {
          slug: 'form',
          title: 'Form',
          active: false,
        },
        {
          slug: 'settings',
          title: 'Réglages',
          active: false,
        },
      ],
      activePage: 'counter',
    }
  },
  methods: {
    changeActive(slug) {
      this.tabulation.forEach(tab => {
        if (tab.slug === slug) {
          tab.active = true;
          this.activePage = tab.slug;
        }
        else{
          tab.active = false;
        }
      })
    }
  }
}
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
nav{
  background: white;
  border-bottom: 1px solid grey;
  padding: 0 20px;
}
nav ul{
  list-style: none;
  padding: 0;
}
nav ul li{
  cursor: pointer;
  font-size: 25px;
  display: inline-block;
  margin: 0 10px;
}

.active{
  background-color: #3498db;
  color: white;
  padding: 10px;
}
</style>
