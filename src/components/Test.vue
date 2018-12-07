<template>
    <div class="test">
        <h4>{{title}}</h4>
        <p>Displayed as v-model: <input type="text" v-model="title"/></p>
        <span>User Name: {{user.fn}} {{user.ln}}</span>
        <p>Displayed as v-text: <span v-text="user.fn"></span></p>
        <p>Displayed as v-html: <span v-html="htmlVal"></span></p>
        <p>Disaplyed as v-if and v-else opposite to this: <span v-if="showVal">Hi all :)</span></p>
        <p>Displayed as v-for: 
            <span v-for='tech in technology'>{{tech.title}}, </span>
        </p>
        <p>Button click action: <button v-on:click="callFunction('Hai')">Click me to show your name</button></p>
        <p>Displayed as keyup & assigned value to component data: 
            <input type="text" v-on:keyup="callMeKeyup"/><span>{{emptyVal}}</span>
        </p>
        <b>Computed properties</b><br>
        First Name: <input type="text" v-model="user.fn"/><br>
        Last Name: <input type="text" v-model="user.ln"/>
        <h3>Returned from computed: {{fullName}}</h3>
        <h4>Value passed from componet props: {{msg}}</h4>
        <hr>
    </div>
</template>

<script>
export default {
    name : 'test',
    components:{},
    props:{
        msg:{
            type: String
        }
    },
    data(){
        return{
            title: "Sathish Test Component title",
            user:{
                fn: "sathish",
                ln: "kumar"
            },
            htmlVal: "<b>Value from b tag</b>",
            showVal: true,
            technology:[
                {title: "ReactJS"},
                {title: "AngularJS"},
                {title: "EmberJS"},
                {title: "KnockoutJS"},
                {title: "Polymer"},
                {title: "HandlebarJS"}
            ],
            emptyVal: ""
        }
    },
    methods: {
        callFunction: function(val) {
            alert(val+" "+this.user.fn+" "+this.user.ln)
        },
        callMeKeyup: function(event){
            this.emptyVal = event.target.value;
        }
    },
    computed: {
        fullName: function() {
            return this.user.fn+" "+this.user.ln;
        }
    }
}
</script>

<style scoped>
ul{
    list-style-type: none
}
</style>

