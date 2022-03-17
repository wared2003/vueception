<template>
    <div class="tasks">
        <div class="task" :key="task" v-for="task in tasks">
            <input @click="checkTask(tasks.indexOf(task))" :id="tasks.indexOf(task)" type="checkbox">
            <label :for="tasks.indexOf" :id="'index' + tasks.indexOf(task)">{{ task.name }}</label>
            <button @click="removeTask(tasks.indexOf(task))" class="fa fa-trash">🗑</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ToDoList',
    props: {
        tasks: {
            type: Array,
            default: () => []
        },
        name: {
            type: String
        }
    },
    
    methods: {
        removeTask(task) {
            this.$emit('removeTask', task)
        },

        checkTask(task) {
            let checkbox = document.getElementById(task)

            if(checkbox.checked) {
                document.getElementById('index' + task).className = "checked"
            } else {
                document.getElementById('index' + task).className = "unchecked"
            }
        }
    
    }
}
</script>

<style>

.task {
    padding: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.unchecked {
    text-decoration: none;
}

.checked {
    text-decoration: line-through;
}

</style>