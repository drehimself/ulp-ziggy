<template>
    <div>
        <div v-for="user in users" :key="user.id">
            {{ user.name }}
        </div>
    </div>
</template>

<script>
    export default {
        mounted() {
            axios.get(route('users.index'))
                .then(response => {
                    this.users = response.data
                })
        },
        data() {
            return {
                users: []
            }
        }
    }
</script>
