<template>
    <div>
        <input type="name" name="name" id="" v-model="fullName">
        <button v-on:click="addName">ADD</button>
        <ul>
            <li v-for="name in names" v-bind:key="name">
                {{name}}
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        name: "updateList",
        data() {
            return {names:[
                'Bob',
                'Daniel',
                'Mark'
            ]}
        },
        methods: {
            addName: function(){
                return this.names.push(this.fullName)
            },
        }
    }
</script>