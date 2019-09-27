<template>
    <div v-if="user">
        {{ user.name }}
    </div>
</template>

<script>
    export default {
        mounted() {
            axios.get(route('users.show', 1))
                .then(response => {
                    this.user = response.data
                })
        },
        data() {
            return {
                user: null
            }
        }
    }
</script>
