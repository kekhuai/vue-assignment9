<template>
    <div class="form-group">
        <label for="firstName">First Name</label>
        <input type="text" class="form-control" id="firstName" :value="firstName" @input="updateFirstName">
        <label for="lastName">Last Name</label>
        <input type="text" class="form-control" id="lastName" :value="lastName" @input="updateLastName">
    </div>
</template>

<script>
    export default {
        props: ['value'],
        computed: {
            firstName() {
                return this.value.split(' ')[0];
            },
            lastName() {
                return this.value.split(' ')[1];
            }
        },
        methods: {
            updateFirstName(event) {
                var fullName = event.target.value + ' ' + this.lastName;
                this.$emit('input', fullName);
            },
            updateLastName(event) {
                var fullName = this.firstName + ' ' + event.target.value;
                this.$emit('input', fullName);
            }
        }
    }
</script>

