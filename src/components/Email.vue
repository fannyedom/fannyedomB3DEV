<template>
    <div >
        <h1>{{ msg }}</h1>
        <form class="col-md-6">
            <div class="form-group">
                <label for="exampleInputEmail1">Email address</label>
                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Enter email">
                <small id="emailHelp" class="form-text text-muted">Nous ne partagerons pas votre adresse mail.</small>
            </div>
            <div class="form-group">
                <label for="exampleInputPassword1">Password</label>
                <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
            </div>
            <div class="form-check">
                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                <label class="form-check-label" for="exampleCheck1">Check me out</label>
            </div>
            <button type="submit" class="btn btn-outline-success">Validation</button>
        </form>

    </div>
</template>

<script>
    export default {
        name: 'Email',
        props: {
            msg: String
        }

    }
</script>
<style>
    form{
        margin : 15px auto;
        background-color: palevioletred;
        padding: 10%;
        border-radius: 10px;
    }
</style>
