<template>
    <div class="testX">
        <h1>{{ msg }}</h1>
        <b-form-group
                id="fieldset-1"
                label="Enter your pseudo"
                label-for="input-1"
                :invalid-feedback="invalidFeedback"
                :valid-feedback="validFeedback"
                :state="state"
        >
            <b-form-input id="input-1" v-model="name" :state="state" trim></b-form-input>
            <b-button type="submit" variant="outline-success" class="btn">Submit</b-button>
        </b-form-group>
    </div>
</template>

<script>
    export default {
        name : 'Validate',
        props: {
            msg: String
        },
        computed: {
            state() {
                return this.name.length >= 4 ? true : false
            },
            invalidFeedback() {
                if (this.name.length > 4) {
                    return ''
                } else if (this.name.length > 0) {
                    return 'Enter at least 4 characters'
                } else {
                    return 'Please enter something'
                }
            },
            validFeedback() {
                return this.state === true ? 'Thank you' : ''
            }
        },
        data() {
            return {
                name: ''
            }
        }
    }
</script>
<style>
    .testX{
        padding: 10px;

        margin: 30px auto;
        border-radius: 10px;
    }
</style>

