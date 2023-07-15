<template>
    <form @submit="onSubmit" >
        <label class="form-control-label" for="task">Task</label>
        <input v-model="text" class="form-control" type="text" id="task">

        <label class="form-control-label" for="data&day">Date&Day</label>
        <input v-model="day" class="form-control" type="text" id="data&day">

        <div class="reminder">
            <label class="form-control-label" for="">Set reminder</label>
            <input v-model="reminder" type="checkbox">

        </div>
        <button class="btn">Save Task</button>
    </form>
</template>

<script>

export default {
    data() {
        return {
            text: '',
            day: '',
            reminder: false
        }
    },

    methods: {
        onSubmit(e) {
            e.preventDefault();
            if (!this.text) {
                alert('please inter tetx')
                return
            }
            const newTask = {
                id: Math.floor(Math.random() * 1000),
                text: this.text,
                day: this.day,
                reminder: this.reminder
            }

            this.$emit('add-task',newTask)

            this.text = ''
            this.day = ''
            this.reminder = ''
        }
    },

}

</script>

<style lang="css" scoped>
form {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.form-control {
    padding: 8px;
    outline: none;
    margin: 5px 0;
}

.form-control-label {
    font-size: 18px;
}

.reminder {
    margin: 5px 0;
    display: flex;
    justify-content: flex-start;
    gap: 100px;
    align-items: center;
}

.reminder input {
    width: 15px;
    height: 15px;
}

.btn {
    padding: 8px;
    background-color: black;
    color: white;
}
</style>