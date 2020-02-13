<template>
    <div class="hello mt-4">
        <h1>{{ msg }}</h1>
        <div >

            <p>Dolor sit amet, consectetur adipisicing elit. Id maxime repellat repellendus porro voluptas laudantium similique eveniet quis perferendis beatae commodi sunt ullam provident dolorum doloribus esse accusamus dolores. Corrupti.</p>
            <p>Numquam delectus recusandae nesciunt rem itaque harum corporis maxime hic iste molestias adipisci excepturi ullam libero necessitatibus cum eum modi minus obcaecati est nemo quia velit earum perferendis consectetur porro?</p>
            <p> Visit my website <a href="https://bootstrap-vue.js.org/docs/components/form-input" target="_blank" rel="noopener">bootstrap vue</a>.</p>
        </div><!--/.col-xs-12 -->

    </div>
</template>

<script>
    export default {
        name: 'HelloWorld',
        props: {
            msg: String
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        display: inline-block;
        margin: 0 10px;
    }
    a {
        color: #ABFF99;
    }
    .hello{
        margin : 15px auto;
        background-color: darkkhaki ;
        padding: 10%;
        border-radius: 10px;
    }
</style>
