<template>
    <div id="ntd">
        <input type="text" v-model="task" placeholder="Entrer votre tâche">
        <button class="add-btn" v-on:click="sendTask(task)">+</button>
    </div>
</template>

<script type="text/javascript">

export default {
    el: "#ntd",

    name: "NewToDo",

    methods: {
        sendTask(task) {
            if(task != "") {
                this.$emit('newTask', this.task)
                this.task = ""
            } else {
                alert('Soit t\'as une belle vie, soit ta tâche est vide ;)')
            }
        }
    },
    
    data() {
        return {
            task: "",
        }
    }

}

</script>

<style scoped>

#ntd {
  width: 50%;
  margin: 0 auto;
  border: none;
}

#ntd input {
  border: none;
  border-bottom: 2px solid #6EC37C;
  outline: none;

}

#ntd input::placeholder {
  text-align: center;
}

.add-btn {
  width: 40px;
  height: 40px;
  background-color: #6EC37C;
  color: #FFFFFF;
  border-radius: 40px;
  border: none;
  font-size: 30px;
}

</style>
