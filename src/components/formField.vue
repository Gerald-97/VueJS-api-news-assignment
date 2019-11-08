<template>
    <form v-on:submit.prevent="submitForm">
        <div class="form__item">
            <label for="name">Name: </label>
            <input type="name" name="name" id="" v-model="fullName">
        </div>
        <div class="form__item">
            <label for="email">Email Address: </label>
            <input type="email" name="email" id="" v-model="email">
        </div>
        <div class="form__item">
            <label for="phone">Contact: </label>
            <input type="tel" name="phone" id="" v-model="phone">
        </div>
        <button type="submit">Submit</button>
        <button v-on:click.prevent='clearForm'>Clear</button>
        <div>
            <p v-html="fullName"></p>
            <p v-html="email"></p>
            <p v-html="phone"></p>
        </div>
    </form>
</template>
<script>
    export default {
        name: "formField",
        data() {
            return{
                fullName: '',
                email: '',
                phone: ''
            }
        },
        methods: {
            submitForm(){
                alert('Welcome ' + this.fullName)
            },
            clearForm(){
                this.fullName = '',
                this.email = '',
                this.phone = ''
            }
        }
    }
</script>
<style scoped>
    form {
        max-width: 400px;
        background: rgb(226, 194, 252);
        padding: 2rem;
        border-radius: 4px;
        margin: 0 auto;
    }
    .form__item {
        display: block;
        width: 100;
        margin-bottom: 1rem;
    }
    .form__item > label {
        display: block;
    }

    .form__item > input {
        padding: 1rem;
        font-size: 18px;
        border-radius: 8px;
        color: black;
        background: #fff;
        border: 2px solid rgb(137, 183, 252);
    }
    button {
        padding: 1rem 3rem;
        background: rgb(71, 68, 68);
        color:#fff;
    }
</style>