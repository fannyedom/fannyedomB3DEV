
<template>
    <div class="aside">
        <h1>Colonne de droite</h1>
        <p>
            lorem ipsum, accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident, similique sunt in culpa qui officia deserunt mollitia animi, id est laborum et dolorum fuga. Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi optio cumque nihil
        </p>
        <div>
            <b-card
                    title="Card Title"
                    img-src="https://picsum.photos/600/300/?image=25"
                    img-alt="Image"
                    img-top
                    tag="article"

                    class="mb-2"
            >
                <b-card-text>
                    Some quick example text to build on the card title and make up the bulk of the card's content.
                </b-card-text>

                <b-button href="#" variant="success">Go somewhere</b-button>
            </b-card>
        </div>

        <InputBlock
                v-bind:class="inputdemerde.class"
                v-bind:value="inputdemerde.value"
                v-bind:placeholder="inputdemerde.placeholder"
                v-on:input="inputdemerde.value = $event">
            texte a mettre dans le Slot par défaut
            <template v-slot:label>Texte dans le Slot Label</template>
            <template v-slot:message>{{inputdemerde.message}}</template>
        </InputBlock>



        <hr/>
    </div>
</template>

<script>
    // @ is an alias to /src
    import InputBlock from '@/components/InputBlock.vue'
    export default {
        name: 'rightcol',
        components: {
            InputBlock
        },
        data () {
            return {
                inputdemerde: {
                    value: '',
                    placeholder: 'placeholder de l\'input',
                    class: '',
                    message: 'message par défaut'
                }
            }
        },
        watch: {
            'inputdemerde.value': function (val) {
                if (val.length < 5) {
                    this.inputdemerde.class = 'error'
                    this.inputdemerde.message = 'trop court'
                } else {
                    this.inputdemerde.class = ''
                    this.inputdemerde.message = 'ok !'
                }
            }
        }
    }
</script>

<style scoped="scoped">
    .error {
        background-color: #ff5555;
    }
   .aside{
       background-color: rgba(192,255,195,0.4);
       padding: 20px;
       border-radius: 10%;
   }

</style>

