let vm = new Vue({
        el: '#app',
        data: {
            title: 'ToDoList !',
            task: null,
            tasks: [],
            lgi: 'list-group-item',
            pending: 'bg-secondary',
            done: 'bg-success',
            mt: 'mt-2',
            success: 'text-success',
            warning: 'text-warning',
            icon: 'icons fas fa-check-square'
        },
        methods: {
            addTask: function() {
                this.tasks.push({id: Date.now(), description: this.task, done: false, isInEditMode: false});
                console.log('tasks', this.tasks);
                this.task = '';
            },
            editMode: function(task) {
                task.isInEditMode = !task.isInEditMode;
                console.log(task)
            },
            deleteTask: function(task) {
                this.tasks = this.tasks.filter(function(t) {
                    return t.id !== task.id;
                })
            },
            itIsDone: function(task) {
                console.log(task.done)
                task.done = true;
            }
        }
    })