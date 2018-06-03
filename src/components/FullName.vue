<template>
    <div class="form-group">
        <label for="firstName">First Name</label>
        <input type="text" class="form-control" id="firstName" :value="firstName" @change="updateFirstName">
        <label for="lastName">Last Name</label>
        <input type="text" class="form-control" id="lastName" :value="lastName" @change="updateLastName">
    </div>
</template>

<script>
    export default {
        props: ['firstName', 'lastName'],
        methods: {
            updateFirstName() {
                this.$emit('input', this.firstName);
            },
            updateLastName() {
                this.$emit('input', this.lastName);
            }
        }
    }
</script>

