# VueJS

# Basic functionalities of VUEJS framework

## Build Setup

``` bash
# Install vue-cli to use vue commands
>npm install -g vue-cli

# Vue app creates with webpack
>vue init webpack <Project Name>

# Then install npm dependencies
>cd <Project Name>
>npm install

# Runs the Vue app in https://localhost:8000
>npm run dev

#For external source
>npm install vue-resource --save
```


BASIC FUNCTIONALITIES USED:

TEST Component:
  * Default data binding through {{}}
  * #v-model -> To store vue object in input elements
  * #v-text -> To display vue object inside HTML elements
  * #v-html -> To accept html based string
  * #v-if & #v-else -> Perform if(){}else{} action based on vue object assigned
  * #v-for -> Iterate array of objects in template
  * #v-on:click & #v-on:keyup -> Triggers click & keyup action
  * Assigns value to emptyObject through keyup
  * Use of computed function
  * Props value passing done in Test component
  
USERS Component:
  * Lists N number of users 
  * Initial datas are retrieved from API
  * $http.get() will work by installing "npm install vue-resource --save"
  * Add functionality to add new user
  * Delete functionality deletes the selected user
  * Strike action given for selected user
  * created() function used like constructor in vueJS
  
ROUTING:
  * We can install "vue-router" by seperatedly or in initial configuration of VueApp
  * Initially test page will be displayed
  * Routing given for Users page
  
 
  ***SCREENSHOTS***
  
1. TEST Compoent VIEW:
![capture](https://user-images.githubusercontent.com/19771986/49641045-1a85ff00-fa35-11e8-9efc-213bed4d48b0.PNG)
![capture2](https://user-images.githubusercontent.com/19771986/49641043-19ed6880-fa35-11e8-9097-a4558adcb52a.PNG)

2. USER Component VIEW
![capture4](https://user-images.githubusercontent.com/19771986/49641044-19ed6880-fa35-11e8-93aa-e84f83d8dc65.PNG)
