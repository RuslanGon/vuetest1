<template>
    <div class="users">
        <h3>{{ el.name }}</h3>
        <p>{{ el.email }} --- {{ el.pass }}</p>
    </div>
</template>

<script>
export default {
    props: {
        el: {
            type: Object,
            required: true
        }

    }
}

</script>

<style scoped></style>