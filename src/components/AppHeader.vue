<script>
export default {
    props: {
        msg: String
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <header>
        <h1>{{ msg }}</h1>
    </header>
</template>

<style lang="scss" scoped>
h1 {
    margin: 1rem;
}
</style>
