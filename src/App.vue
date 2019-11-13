<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/>
    <testFile msg="This is just a subtitle!!!"/>
    <formField/>
    <updateList/>
    <ContactForm/>
    <todoList/>
    <SearchApp/> -->
    <NewsForm/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import testFile from './components/testFile.vue'
// import formField from './components/formField.vue'
// import updateList from './components/updateList.vue'
// import ContactForm from './components/ContactForm.vue'
// import todoList from './components/todoList.vue'
// import SearchApp from './components/searchApp.vue'
import NewsForm from './components/getForm.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    // testFile,
    // formField,
    // updateList,
    // ContactForm,
    // todoList,
    // SearchApp,
    NewsForm

  },
  data(){
    return{
      
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
