<template>
    <div>
        <form>
            <h1>To-do List</h1>
            <input type="item" v-model="entry">
            <button v-on:click.prevent="addToList">Add to List</button>
        </form>
        <table>
            <thead>
                <tr>
                    <th>Things to do</th>
                    <th>Delete</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, index) in list" v-bind:key="index">
                    <td>{{item}}</td>
                    <td>
                        <button v-on:click="deleteKey(index)" >Delete Item</button>
                    </td>
                </tr>
            </tbody>
        </table>
        <h4>You have {{totalItems}} things to do</h4>
        <h4>You have deleted {{deletedItems}} things</h4>
    </div>
</template>
<script>
export default {
    name: 'To-doList',
    data(){
        return{
            list:[],
            entry:'',
            deletedItems:0
        }
    },
    methods:{
        addToList(){
            this.list.push(this.entry);
            this.entry = ''
        },
        deleteKey(index){
            this.list.splice(index, 1);
            this.deletedItems += 1
        }
    },
    computed:{
        totalItems(){
            let total = 0;
            total += this.list.length;
            return total;
        }
    }
}
</script>
<style scoped>
    form {
        max-width: 400px;
        background: rgb(163, 191, 245);
        padding: 2rem;
        border-radius: 8px;
        margin: 40px auto;
    }
    input {
        padding: 1rem;
        font-size: 18px;
        border-radius: 8px;
        color: black;
        background: #fff;
        border: 2px solid rgb(163, 191, 245);
        width: 90%;
    }
    button {
        padding: 0.1rem 0.5rem;
    }
    table {
        border: 1px solid black;
        width: 100%;
    }
    td, th {
        border: 1px solid black;
        padding: 1rem;
    }
    tr:nth-child(even) {
        background: #dbdbdb;
    }
</style>