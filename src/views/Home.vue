
<template>
    <div class="home">
        <NavComponent/>

        <HelloWorld msg=" Welcome!"/>
        <Texte/>
        <div>



            <router-link to="/About"  class="btn btn-outline-success" role="button">CTA</router-link>
        </div>
        <br>
        <input type="text" v-model="keyword" v-on:keyup.enter="searchNearBy" class="form-control premierinput">
        <br>

        <div
                :key="index"
                v-for="(m, index) in markers">
            {{ m.name }}
        </div>

        <GmapMap ref="mapRef"
                 :center="{lat:10, lng:10}"
                 :zoom="12"
                 map-type-id="terrain"
        >
            <GmapMarker
                    :key="index"
                    v-for="(m, index) in markers"
                    :position="m.geometry.location"
                    :title="m.name"
                    :clickable="true"
                    :draggable="false   "
                    @click="openInfoWindowTemplate(m)"
            >
            </GmapMarker>
            <GmapInfoWindow
                    :options="{maxWidth: 300}"
                    :position="infoWindow.position"
                    :opened="infoWindow.open"
                    @closeclick="infoWindow.open=false">
                <!-- ici on utilise v-html et pas {{ }} car il est possible qu'on balance du html dans la div et qu'on souhaite l'interpreter -->
                <div v-html="infoWindow.template"></div>

            </GmapInfoWindow>
        </GmapMap>

        <Email msg="Souhaitez-vous vous inscrire ?!"/>

        <Video/>
<Validate msg=" N'hésite pas à t'inscrire"/>
        <Apropos msg=" A propos!" />




    </div>

</template>

<script>
    // @ is an alias to /src
    import HelloWorld from '@/components/HelloWorld.vue'
    import Apropos from '@/components/Apropos.vue'
    import Video from '@/components/Video.vue'
    import Email from '@/components/Email.vue'
    import Texte from "../components/Texte"
    import NavComponent from "../components/NavComponent"
    import Validate from "../components/Validate";



    export default {
        name: 'home',
        components: {
            Validate,
            NavComponent,
            Texte,
            Email,
            Video,
            Apropos,
            HelloWorld
        },
        data () {
            return {
                keyword: 'yolo',
                markers: [],
                infoWindow: {
                    position: {lat: 0, lng: 0},
                    open: false,
                    template: ''
                }
            }
        },
        methods: {
            searchNearBy(){
                this.$refs.mapRef.$mapPromise.then((map) => {
                    /* eslint-disable no-undef */
                    //let targetLatLng = new google.maps.LatLng(48.864716, 2.349014)
                    map.panTo({lat: 48.864716, lng: 2.349014})
                    // map.panTo({lat: 48.864716, lng: 2.349014})
                    /* eslint-disable no-undef */
                    let placesService = new google.maps.places.PlacesService(map)
                    placesService.nearbySearch({
                        location: {lat: 48.864716, lng: 2.349014},
                        name: this.keyword,
                        radius: 1000,
                        // types: ['store', 'restaurant']
                    }, (results, status) => {
                        this.markers = results
                        console.log(status)
                    })
                })
            },
            openInfoWindowTemplate (item) {
                this.infoWindow.template = '<img alt="Vue logo" src="'+ item.icon +'"><h1>' + item.name +'</h1>'
                this.infoWindow.position = item.geometry.location
                this.infoWindow.open = true
            }
        },
        mounted () {
            // At this point, the child GmapMap has been mounted, but
            // its map has not been initialized.
            // Therefore we need to write mapRef.$mapPromise.then(() => ...)
            this.searchNearBy()
        }
    }
</script>
<style scoped>
    .vue-map-container {
        width: 100%;
        height: 400px;
    }
    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
    }

    .btn-success{
        margin: 15px;
    }
</style>


