<template>
    <div>
        <h1>{{ webtitle }}</h1>
        <div v-text="txtHtml"></div>
        <div v-html="txtHtml"></div>
        <div v-if="valText">
            {{ user.firstName }}
        </div>
        <div v-else>
            <small> No puedo mostrar el Nombre. El vlor es "{{ valText }}"</small>
        </div>
        <hr>
        <ul>
            <li v-for="t in tasks">
                {{ t.detail }} - {{ t.id }}
            </li>
        </ul>

        <div>
            <button v-on:click="saludar(user.firstName)"> CLICK ME </button>
            <input type="text" v-model="user.firstName">
        </div>

        <hr>

        <div>
            <h1>Typing consoles</h1>
            <div>
                <input type="text" v-on:keyup="typing">
            </div>
            <h1>Typing Enter</h1>
            <div>
                <input type="text" v-on:keyup.enter="typedEnter">
            </div>
        </div>

        <hr>

        <div>
            <h1>Objetos computados</h1>
            <p>
                {{ fullName }}
            </p>
        </div>

        <div>
            <h1>Props</h1>
            <p>
                {{ msg }}
            </p>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Test",
        data(){
            return {
                webtitle: "New component Test XD",
                user: {
                    firstName: "Kevin",
                    lastName: "QL"
                },
                txtHtml: "<h3>Texto dentro de un H3</h3>",
                valText: false,
                tasks: [
                    {
                        id: 1,
                        detail: "weak up"
                    },
                    {
                        id: 2,
                        detail: "shower"
                    },
                    {
                        id: 3,
                        detail: "break"
                    },
                ]
            }
        },
        methods: {
            saludar(name){
                alert("hello " + name);
            },
            typing(e){
                console.log(e.target.value);
            },
            typedEnter(e){
                console.log("Se dió enter " + e.target.value)
                alert(":o Enter!!")
            }
        },
        computed: {
            fullName(){
                return this.user.firstName + ' ' + this.user.lastName;
            }
        },
        props : {
            msg: {
                type: String,
                default: "mdj por defecto"
            }
        }
    }
</script>


<style>

</style>