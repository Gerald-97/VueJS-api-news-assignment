<template>
    <div>
        <h1>ThIS IS ME!!!</h1>
        <h3>{{ msg }}</h3>
    </div>
</template>
<script>
export default {
    name: "testFile",
    props: {
    msg: String
  }
}
</script>
<style scoped>
h1{
    color: red;
}
</style>