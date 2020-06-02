<template>
    <div id="app-signup" class="signup container">
        <div class="row">
            <h2 class="col-sm-6 text-center">Sign Up</h2>
            <form @submit="formSubmit" class="form col-sm-6 col-md-4">
                <p class="status">
                    <small>{{this.status}}</small>
                </p>
                <fieldset>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">Email</label>
                        <input class="input col-sm-6 col-md-3" placeholder="john.doe@e-male.com" type="email" v-model="email"/>
                    </div>
                    <div class="input-group row">
                        <label class="col-sm-6 col-md-3">Password</label>
                        <input class="input col-sm-6 col-md-3" type="password" v-model="password"/> 
                    </div>
                    <div class="input-group row">
                        <input class="button button--inverted" type="reset" value="Reset"/>
                        <input class="button" type="submit" value="Sign Up"/>
                    </div>
                </fieldset>
            </form>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'app-signup',
    data() {
        return {
            email: '',
            password: '',
            status: ''
        }
    },
    methods: {
        formSubmit(e) {
            e.preventDefault();
            axios.post('https://reqres.in/api/register', {
                email: this.email,
                password: this.password
            })
            .then(response => {this.status = 'Thanks! Your account has been successfully created!'; console.log(response)})
            .catch(error => {this.status = error.response.data.error; console.log(error.response)})
            .finally(() => this.loading = false)
        }
    }
}
</script>