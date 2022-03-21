<template>

<div class="container">

    <div class="nav">
        <p>{{ date }}</p>
        <h1>VueJs Tutorial ToDo List</h1>
        <p>Nombre de tâches : {{ tasks.length }}</p>
    </div>
    <div>

        <NewToDo @newTask="addTask"></NewToDo>

        <ToDoList v-bind:tasks="tasks" @removeTask="removeTask"></ToDoList>
      <div v-if="incrementStater">

        <p>on ajoute un handler de l'evenement click qui appelle la method addTask</p>
        <img src="../assets/increment1.png"/>
        <p>on ajoute au tableau tasks la tache, on verifie si il faut afficher le tutoriel</p>
        <img src="../assets/increment2.png" />
      </div>


    </div>
</div>


</template>

<script type="text/javascript">


import NewToDo from './NewToDo.vue'
import ToDoList from './ToDoList.vue'

export default {
    name: "ToDoCard",

    components: {
        NewToDo,
        ToDoList
    },

    data() {

        return {
            incrementStater: false,
            day: ["Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi", "Dimanche"],
            month: ["Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Août", "Septembre", "Octobre", "Novembre", "Décembre"],
            tasks: [],

        }

    },
    computed: {

        date: function() {
            let today = new Date();
            let todate = `${this.day[(today.getDate())-1]}` + ' ' + today.getDay() + ' ' + `${this.month[(today.getMonth())]}` + ' ' + today.getFullYear();
            return todate
        }

    },

    methods: {

        addTask(task) {
            this.tasks.push({name: task, state: 0})
          //afficher les tutoriel correspondant aux taches
            if(task == "ajouter une tache"){
              this.incrementStater = true;
            }
        },
        
        removeTask(task) {
            this.tasks.splice(task, 1)
        }
    }
}
</script>

<style scoped>

.nav {
  border-bottom: 1px solid #dddddd;
  box-shadow: 0 0 2px;
  margin-bottom: 10px;
}

.container {
    width: 600px;
    min-height: 300px;
    background-color: #FFFFFF;
}

.container div:first-of-type {
    display: flex;
    justify-content: space-around;

}

.container div:first-of-type h1 {
    color: #85D9C6;
    padding: 10px 0;
    font-weight: bold;
}

</style>
