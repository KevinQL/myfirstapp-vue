<template>
    <div class="container-user">
        <h1>Componente Usuarios</h1>
        <ul>
            <li v-for="user in users">
                {{ user.name }} - {{ user.email }} - <button v-on:click="deleteUser(user)">x</button>
            </li>
        </ul>
        <form v-on:submit.prevent="addUser">
            <input type="text" v-model="newUser.name" placeholder="Ingrese nombre">
            <input type="email" v-model="newUser.email" placeholder="Ingrese correo">
            <button type="submit">
                Add
            </button>
        </form>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                users: [ ],
                newUser: {}
            }
        },
        methods: {
            addUser(){
                console.log("Agregando usuario nuevo");
                this.users.push(this.newUser);
                this.newUser = {}
            },
            deleteUser(user){
                this.users.splice(this.users.indexOf(user), 1);
                console.log("Se eliminó", user)
            }
        },
        created(){
            console.log('componente cargado y creado!!')
            this.$http.get('https://jsonplaceholder.typicode.com/users')
            .then(res => this.users = res.body);
        }
    }
</script>

<style>
    .container-user{
        background-color: blueviolet;
        color: white;
        padding: 10px;
    }
</style>