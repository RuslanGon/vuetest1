<template>
    <div class="users">
        <h3>{{ el.name }}</h3>
        <p>{{ el.email }} --- {{ el.pass }}</p>
        <button @click="deleteUser(index)">delete user</button>
    </div>
</template>

<script>
export default {
    props: {
        el: {
            type: Object,
            required: true
        },
        index: {
            type: Number,
            required: true
        },
        deleteUser: {
            type: Function,
            required: true
        }

    }
}

</script>

<style scoped></style>