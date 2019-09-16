<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm {{name}}</p>
        <p>age:{{age}}</p>
        <button @click="changeName">Change My Name</button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">
                <app-user-detail 
                :name="name" 
                @nameWasReset="name = $event"
                :resetFn="resetName"
                :userAge='age'></app-user-detail>
            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit 
                :userAge="age"
                @ageWasChanged="age=$event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data: function(){
            return {
                    name: 'Aadil',
                    age: 23
                
            };

        },
        methods:{
            changeName(){
                this.name='Muhammad Aadil';
            },
            resetName(){
                this.name="Aadil";
            }

        },

        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
