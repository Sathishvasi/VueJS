<template>
    <div class="users">
        <h3>User component</h3>
        <input type="text" placeholder="User Name" v-model="emptyObj.un"/><br>
        <input type="text" placeholder="Email" v-model="emptyObj.em"/><br>
        <button v-on:click="addUser">Add user</button>
        <br>
        <h4>Initial user values from API</h4>
        <ul>
            <li v-for="user in users">
                <input type="checkbox" class="toggle" v-model="user.contacted"/>
                <span :class="{contacted: user.contacted}">
                    <b>{{user.name}}:</b> {{user.email}}
                    <button v-on:click="deleteUser(user)">x</button>
                </span>
            </li>
        </ul>
        <hr>
    </div>
</template>

<script>
export default {
    name : 'users',
    props:{
        msg:{
            type: String
        }
    },
    data(){
        return{
            emptyObj:{},
            users:[
                // {
                //     name: "Sathish",
                //     email: "sathish@wizroots.com",
                //     contacted: false
                // },
                // {
                //     name: "Gowtham",
                //     email: "gowtham@wizroots.com",
                //     contacted: false
                // },
                // {
                //     name: "Robin",
                //     email: "robin@wizroots.com",
                //     contacted: false
                // },
                
            ]
        }
    },
    methods: {
        addUser: function(e) {
            if(this.emptyObj.un!="" && this.emptyObj.em!=""){
                this.users.push({
                    name: this.emptyObj.un,
                    email: this.emptyObj.em,
                    contaced: false
                })
            }else{
                alert("Fill all fields")
            }
            console.log(this.emptyObj.un)
            console.log(this.emptyObj.em)
        },
        deleteUser: function(user){
            this.users.splice(this.users.indexOf(user), 1)
        }
    },
    created: function() {
        this.$http.get('https://jsonplaceholder.typicode.com/users')
        .then(function(response){
            console.log(response.data)
            this.users = response.data;
        })
    }   
}
</script>

<style scoped>
ul{
    list-style-type: none
}
.contacted{
    text-decoration: line-through;
}
</style>

