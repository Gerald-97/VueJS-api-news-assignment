<template>
    <div class="container">
        <input type="name" name="name" id="" v-model="fullName">
        <ul id="nameList">
            <li v-for="item in items">
                {{item.name}}
            </li>
        </ul>
    </div>
</template>