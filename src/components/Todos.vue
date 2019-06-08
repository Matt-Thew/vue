<template>
    <div>
        <div v-for="todo in todosapp">
            <h3>{{ todo.name }}</h3>

        </div>
    </div>
</template>

<script>
export default {
    name: "Todos",
    props: ["todosapp"]
}
</script>

<style scoped>

</style>
