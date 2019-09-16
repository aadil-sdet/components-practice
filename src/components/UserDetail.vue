<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{name}}</p>
        <p>User Age:{{userAge}}</p>
        <button @click="resetFn()">Reset Name</button>
    </div>
</template>

<script>
export default{
    props: {
        name: String,
        resetFn : Function,
        userAge: Number 
    },
    methods:{
        resetName(){
            this.name='Adil Reset';
            this.$emit('nameWasReset' , this.name);
        }

    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
