<template>
    <div id="lineas">
    </div>
    <div id="DescripcionBreve">
        <div class="titulo">
            <h1 class="grande">GONZALO LECUMBERRI</h1>
        </div>
        <div>
            <p class="mediana sombra" id="sobreMi">
                Sobre mi
            </p>
        </div>
        <p class="pequena" id="descripcion">
            Soy un desarrollador junior enfocado en Backend, especializado en Java y con conocimientos en Frontend usando Vue.js. Me apasiona aprender y enfrentar nuevos desafíos a la hora de programar. Estoy abierto a oportunidades para colaborar en proyectos interesantes y aportar mis habilidades.  <br>
            {{ parrafoRevelado }}
            <span class="blinking-cursor"></span>
        </p>

        <router-link to="/sobreMi" class="btnPaginaInicio">
            <btnComp>Saber mas</btnComp>
        </router-link>
    </div>
</template>

<script>
import btnComp from '@/components/btns/btnComp.vue';
export default{
    components:{
        btnComp
    },
    data(){
        return{
            parrafo: "Si buscas un desarrollador comprometido y entusiasta, no dudes en contactarme.",
            parrafoRevelado: ""
        };
    },
    mounted(){
        this.revelarTexto();
    },
    methods:{
        revelarTexto(){
            const texto = this.parrafo.split("");
            let indexActual = 0;

            const revealInterval = setInterval(() =>{
                if (indexActual < texto.length){
                    this.parrafoRevelado += texto[indexActual];
                    indexActual++;
                }else{
                    clearInterval(revealInterval);
                }
            },15);
            const updateView = () => {
                this.$forceUpdate();
                if (indexActual < texto.length) {
                    requestAnimationFrame(updateView);
                }
            };
            
            requestAnimationFrame(updateView);
        }
    }
}
</script>

<style>
    #DescripcionBreve{
        width: 80%;
        margin-left: 3%;
        display: flex;
        flex-direction: column;
        z-index: 1;
        height: 100vh;
    }

    #sobreMi{
        color: rgba(134, 194, 50, 1);
    }

    #descripcion{
        width: 90%;
        margin-top: 2rem;
        margin-bottom: 2rem;
        border-left: solid 2px rgba(97, 137, 47, 1);
        padding-left: 1rem;
        height: auto;
        color: rgb(161, 165, 168);
    }

    .blinking-cursor {
        display: inline-block;
        width: 1px;
        height: 1.2em;
        background-color: #000; /* Color de la barra parpadeante */
        animation: blink 0.8s infinite;
        vertical-align: middle;
    }

        @keyframes blink {
        0%, 100% {
            opacity: 0;
        }
        50% {
            opacity: 1;
        }
    }

    .btnPaginaInicio{
        align-self: center;
    }

    .titulo{
        color: white;
        text-shadow: 8px 6px 0px #116e437a;
        margin: 4rem 0 2rem 0;
    }


    @media  screen and (max-width:767px) {
        #DescripcionBreve{
            width: 100%;
        }
        .btnPaginaInicio{
            display: none;
        }
        #descripcion{
            padding-bottom: 6rem;
            height: auto;
            font-size: 1.3rem;
        }
      
  }
</style>
