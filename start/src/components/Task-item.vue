<template>
     <li>
        <button @click="$emit('complete')" v-bind:class="className">
            <i class="fas fa-circle"></i> {{ task.title }}</button>
        <button @click="$emit('remove')">
            <i class="far fa-trash-alt"></i></button>
    </li>
</template>

<script>
export default {
    name : 'TaskItem',
    props: ['task'],
    computed:{
        className(){
            let classes = ['toggle'];
            if(this.task.completed){
                classes.push('toggle-completed');
            }
            return classes;
        }
    },
};
</script>
