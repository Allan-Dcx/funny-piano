<template>
    <div class="Piano">
        <img id="Emoticone" class="m-auto"  >
        <div class="Body_Piano m-auto flex flex-col ">
            <div class="Grandes_Touches lg:mt-3 ">
                <button class="Grande_Touche noteC" @click.prevent="Sound('/assets/sounds/C.mp3')" @click="GifsAnime()"></button>
                <button class="Grande_Touche noteD" @click.prevent="Sound('/assets/sounds/D.mp3')" @click="GifsAnime()"></button>
                <button class="Grande_Touche noteE" @click.prevent="Sound('/assets/sounds/E.mp3')" @click="GifsAnime()"></button>
                <button class="tGrande_Touche noteF" @click.prevent="Sound('/assets/sounds/F.mp3')" @click="GifsAnime()" ></button>
                <button class="Grande_Touche noteG" @click.prevent="Sound('/assets/sounds/G.mp3')" @click="GifsAnime()" ></button>
                <button class="Grande_Touche noteA" @click.prevent="Sound('/assets/sounds/A.mp3')" @click="GifsAnime()"></button>
                <button class="Grande_Touche noteB" @click.prevent="Sound('/assets/sounds/B.mp3')" @click="GifsAnime()"></button>
            </div>
            <div class="Petites_Touches ">
                <button class="Petite_Touche noteC1" @click.prevent="Sound('/assets/sounds/C%23.mp3')" @click="GifsAnime()"  ></button>
                <button class="Petite_Touche noteD2" @click.prevent="Sound('/assets/sounds/D%23.mp3')" @click="GifsAnime()"></button>
                <button class="Petite_Touche noteF3" @click.prevent="Sound('/assets/sounds/F%23.mp3')" @click="GifsAnime()"  ></button>
                <button class="Petite_Touche noteG4" @click.prevent="Sound('/assets/sounds/G%23.mp3')" @click="GifsAnime()" ></button>
                <button class="Petite_Touche noteA5" @click.prevent="Sound('/assets/sounds/A%23.mp3')" @click="GifsAnime()" ></button>
            </div>
            
        </div>
        <div class="Nom_Note flex m-auto ">
            <a class="Note">Do</a>
            <a class="Note">Ré</a>
            <a class="Note">Mi</a>
            <a class="Note">Fa</a>
           <a class="Note">Sol</a>
            <a class="Note">La</a>
            <a class="Note">Si</a>

        </div>
    </div>
</template>

<script>
import { GiphyFetch } from '@giphy/js-fetch-api'

export default {
    data() {
        return {
            gifs:[]
        }
    },
    mounted () {
        this.isPress = false
        this.addListeners()
    },
    methods: {
        
        Sound : function (url) {
            new Audio(url).play() ;
        },
        async GifsAnime() {      
            const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')

            const { data: gifs } =  await gf.emoji()
            console.log(gifs)

            const nbRandom = Math.floor(Math.random() * Math.floor(25)) ;
            console.log(gifs[nbRandom].images['fixed_width'].webp) ;
            const urlRandom = gifs[nbRandom].images['fixed_width'].webp ;
            document.getElementById('Emoticone').src=urlRandom ;
        },
            
    }

}
</script>


<style lang="postcss" scoped>
img {
    height: 280px ;
    width: auto ;
}

@media only screen and (max-width: 767px) {
    .Piano {
        padding-bottom: 35px;
    }
}

.Body_Piano {
    height: 276px ;
    width: 531px ;
    border-radius: 10px ;
    background: black ;
    margin-bottom: 40px ;
    align-items: center ;
    box-shadow: 1px 1px 30px rgb(97, 47, 47) ;
}

@media only screen and (max-width: 767px) {
    .Body_Piano {
        max-height: 190px ;
        max-width: 368px ;
        margin-top: 70px ;
    }
}

@media only screen and (max-width: 767px) {
    #Emoticone {
        margin-top: 100px ;
    }
}

.Piano {
        padding-bottom: 35px;
    }


.Grande_Touche:nth-child(1) {
    height: 252px ;
    width: 69px ;
    background: #FFFFFF ;
    border-radius: 5px 0px 0px 5px ;
}

@media only screen and (max-width: 767px) {
    .Grande_Touche:nth-child(1) {
        height: 173px ;
        width: 47px ;
    }
}

.Grande_Touche:nth-child(7) {
    height: 252px ;
    width: 69px ; 
    background: #FFFFFF ; 
    border-radius: 0px 5px 5px 0px ;
}

@media only screen and (max-width: 767px) {
    .Grande_Touche:nth-child(7) {
        height: 173px ;
        width: 47px ;  
    }
}

.Grande_Touche {
    height: 252px ;
    width: 69px ;
    background: #FFFFFF ;
    margin: 0px 2px ;
}

@media only screen and (max-width: 767px) {
    .Grande_Touche {
        height: 173px ;
        width: 47px ;
    }
}

.Petites_Touches {
    width: 507px ;
    margin-top: -252px ;
    align-items: flex-start ;
}

@media only screen and (max-width: 767px) {
    .Petites_Touches {
        width: 368px ;
        margin-top: -175px ;
    }
}

.Petite_Touche {
    height: 184px ;
    width: 30px ;
    background: #000000 ;
    border-radius: 0px 0px 5px 5px ;
    margin-left: 43px ;
}

@media only screen and (max-width: 767px) {
    .Petite_Touche {
        height: 126px ;
        width: 21px ;
        margin-left: 30px ;
    }
}

.Petite_Touche:nth-child(1) {
    margin-left: 56px ;
}

@media only screen and (max-width: 767px) {
    .Petite_Touche:nth-child(1) {
        margin-left: 46px ;
    }
}

.Petite_Touche:nth-child(2) {
    margin-right: 73px ;
}

@media only screen and (max-width: 767px) {
    .Petite_Touche:nth-child(2) {
        margin-right: 50px ;
    }
}

.Nom_Note {
    width: 422px ;
    justify-content: center ;
    padding-bottom: 34px;
}
.Note {
    text-transform: uppercase ;
    width: 73px ;
    color: rgba(255, 255, 255, 0.4) ;
}

img {
    height: 280px ;
    width: auto ;
}

</style>