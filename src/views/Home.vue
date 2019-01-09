<template>
<div>
  <Header></Header>

  <!--<section class="uk-section" v-if="errored">
      <div class="uk-container tm-container-medium">
        <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
      </div>
    </section>-->

  <!--<div v-else class="uk-section">
    <div class="uk-container say-container-medium">
        <div v-if="loading">Cargando...</div>
        <div>{{ info }}</div>
    </div>
  </div>-->

  <!--<div class="uk-section">
    <div class="uk-container say-container-medium">
      <h3>Agregar Nuevo Proyecto</h3>
      <form  method="post" @submit.prevent="postNow">
      <p>
        <label for="name">Name: {{title}}</label>
        <input type="text" name="name" id="name" v-model="title">
      </p>


      <p>
        <input type="submit" value="Submit">
      </p>
    </form>
    <div v-if="issaved">Guardado Satisfactoriamente</div>
    </div>
  </div>-->

  <div class="uk-section" id="selectedprojects">

    <div class="uk-container say-container-medium">

      <div class="uk-section">
        <p>Proyectos</p>
        <h1>Selectos</h1>
      </div>

      <div class="uk-child-width-1-2@s uk-flex uk-flex-middle" uk-grid uk-scrollspy="cls: uk-animation-slide-bottom-medium; target: > div > div; delay: 300;">

        <Item
        v-for="project in projects"
        v-bind:key="project.id"
        v-bind:item="project"

        ></Item>

      </div>

    </div>

  </div>

  <div class="uk-section uk-section-large">

   <div class="uk-container say-container-medium">
     <div class="almost-middle-container">
       <h1 class="responsive-small">Tú Lo Imaginas</h1>
       <h1 class="responsive-small accent-secondary">Nosotros Lo Creamos</h1>
       <div>
         <p class="uk-width-large@s uk-margin-small-top uk-margin-small-bottom">Somos una agencia digital dedicada al diseño de productos digitales pensada en innovar el mercado chileno, conformada por un equipo joven creativo que se encarga de brindar la máxima experiencia en cuanto a productos digitales y físicos.
         </p>
        <router-link  class="uk-button uk-button-large uk-button-text style-b uk-visible@s" to="/team">Conócenos Más</router-link>
       </div>
     </div>

   </div>
  </div>

  <div class="say-background-secondary">

   <div class="uk-child-width-1-2@m uk-flex uk-flex-middle" uk-scrollspy="target: > div; cls:uk-animation-fade; delay: 500;" uk-grid>
     <div>
       <div >
         <div class="say-padding-left-container">
           <div class="uk-section">
             <div class="uk-container">
               <p class="header-text">Últimos Proyectos</p>
               <h1 class="responsive-small">Federación Chilena de</h1>
               <h1 class="responsive-small accent-secondary">Taekwondo Tradicional</h1>
               <p class="uk-margin-top">Trabajo realizado para la Federación Chilena de Taekwondo Tradicional, se realizó producción de estampado de poleras para un evento deportivo. Se utilizó la técnica de <b>serigrafía</b> para un estampado duradero y de calidad. </p>
               <div class="uk-margin">
                 <ul class="uk-list">
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Estampado de Poleras Publicitarias</p></li>
                 </ul>
               </div>
               <a class="uk-button uk-button-large uk-button-text style-b uk-visible@s uk-margin-top uk-disabled" href="">Ver Proyecto</a>
             </div>
           </div>
         </div>
       </div>
     </div>
     <div>
       <div>
         <img class="uk-width-1-1" src="/assets/components/projects/highlight/side-a.png" alt="">
       </div>
     </div>
   </div>

  </div>

  <div class="say-background-gradient-art">

   <div class="uk-child-width-1-2@m uk-flex uk-flex-middle" uk-scrollspy="target: > div; cls:uk-animation-fade; delay: 500; "  uk-grid>
     <div>
       <div >
         <div class="">
           <div class="uk-section">
             <div class="uk-container">
               <div class="uk-width-xlarge">
                 <p class="header-text">Últimos Proyectos</p>
                 <h1 class="responsive-small">Arte Impreso</h1>
                 <!--<h1 class="responsive-small accent-secondary">Impreso</h1>-->
                 <p class="uk-margin-top">Arte Impreso en una empresa enfocada en la venta de artículos publicitarios a gran escala tales como gigantografías, POP, pendones, etc. Trabajamos en su imagen digital y en la fotografía de sus productos para la plataforma web.</p>
                 <div class="uk-margin">
                   <ul class="uk-list">
                     <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Fotografía de Productos</p></li>
                     <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Diseño UX | UI</p></li>
                     <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Desarrollo e Implementación E-commerce</p></li>
                   </ul>
                 </div>
                 <a class="uk-button uk-button-large uk-button-text style-b uk-visible@s uk-margin-top uk-disabled" href="">Ver Proyecto</a>
               </div>
             </div>
           </div>
         </div>
       </div>
     </div>
     <div class="uk-flex-first@m">
       <div>
         <img class="uk-width-1-1" src="/assets/components/projects/highlight/side-b.png" alt="">
       </div>
     </div>
   </div>

  </div>

  <div class="say-background-digital">

   <div class="uk-child-width-1-2@m uk-flex uk-flex-middle" uk-scrollspy="target: > div; cls:uk-animation-fade; delay: 500; "  uk-grid>
     <div>
       <div >
         <div class="say-padding-left-container">
           <div class="uk-section">
             <div class="uk-container">
               <p class="header-text">Últimos Proyectos</p>
               <h1 class="responsive-small">Asesorías CGV</h1>
               <h1 class="responsive-small accent-secondary">Estudio Contable</h1>
               <p class="uk-margin-top">CGV SPA es una empresa chilena enfocada al rubro de la contabilidad en sus diversos aspectos. Se trabajó conjuntamente para crear e implementar su diseño corporativo, sitio web, tarjetas de presentación, etc.</p>
               <div class="uk-margin">
                 <ul class="uk-list">
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Branding | Identidad Corporativa</p></li>
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Diseño UX | UI</p></li>
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Desarrollo Plataforma Web</p></li>
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Papelería</p></li>
                   <li><p><span class="uk-margin-small-right" uk-icon="icon: check"></span> Fotografía Corporativa</p></li>
                 </ul>
               </div>
               <a class="uk-button uk-button-large uk-button-text style-b uk-visible@s uk-margin-top uk-disabled" href="">Ver Proyecto</a>
             </div>
           </div>
         </div>
       </div>
     </div>
     <div>
       <div>
         <img class="uk-width-1-1" src="/assets/components/projects/highlight/side-c.jpeg" alt="">
       </div>
     </div>
   </div>

  </div>

  <div class="uk-section uk-section-large">
    <div class="uk-container say-container-medium">

       <h1 class="responsive-small uk-text-center">¿Cuáles son nuestros principios?</h1>

       <div class="uk-section">
         <div class="uk-child-width-1-3@l uk-child-width-1-2@m uk-text-center uk-child-width-1-1 " uk-grid>
           <div>
             <div>
               <img src="/assets/components/others/imagine.jpeg" alt="">
               <h3 class="uk-margin">Imagina</h3>
               <p class="uk-margin">Pensamos e idealizamos el diseño de nuestros productos ya sean digitales o físicos pensando en innovar su imagen.</p>
             </div>
           </div>
           <div>
             <div>
               <img src="/assets/components/others/design.jpeg" alt="">
               <h3 class="uk-margin">Expresa</h3>
               <p class="uk-margin">Nos importa expresar tu identidad corporativa frente a tus clientes y público en general sin perder ese toque que te hizo genial.</p>
             </div>
           </div>
           <div>
             <div>
               <img src="/assets/components/others/create.jpeg" alt="">
               <h3 class="uk-margin">Crea</h3>
               <p class="uk-margin">Nos encargamos de crear el producto a través de todo el proceso que este conlleve y así también ustedes puedan ser parte de este.</p>
             </div>
           </div>
         </div>
       </div>

    </div>
  </div>




<!--<Digital></Digital>
<PhotoMarketing></PhotoMarketing>
<Physical></Physical>

<div class="uk-section uk-section-large">

  <div class="uk-container uk-container-large uk-text-left@l uk-text-center">

    <div class="uk-flex uk-flex-middle" uk-grid>

      <div class="uk-width-2-5@l">
        <div class="uk-section uk-section-small">
          <h1 class="responsive">Diseña, Crea & Conoce</h1>
          <h1 class="responsive accent-secondary margin-bottom">Say Community</h1>
          <p class="uk-hidden@l uk-margin-auto uk-width-large">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nostrum dolores asperiores voluptatem veritatis odio est. Repudiandae.</p>
          <p class="uk-visible@l uk-width-large">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nostrum dolores asperiores voluptatem veritatis odio est. Repudiandae.</p>
        </div>
      </div>

     <div class="uk-width-3-5@l">
       <div class="">
         <video  loop muted playsinline uk-video="autoplay: inview">
         <source src="/assets/components/community/intro.mp4" type="video/mp4">
         </video>
       </div>
     </div>

    </div>

  </div>

</div>

<div class="uk-section">

<div class="animation-container">
  <h1 ref="text">That's me, </h1>
  <div id="animation" ref="animation"></div>
</div>

</div>-->


</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/home/Header.vue'
import Team from '@/components/home/Team.vue'
import Physical from '@/components/home/Physical.vue'
import Digital from '@/components/home/Digital.vue'
import PhotoMarketing from '@/components/home/PhotoMarketing.vue'
import Footer from '@/components/Footer.vue'
import Item from '@/components/Item.vue'
import {TweenMax, Power4, TimelineLite} from "gsap/TweenMax"
import axios from 'axios'

axios.defaults.headers.common['X-AUTH-TOKEN'] = '904e011eecb68c0cadc4f885df110f76'

export default {
  name: 'home',
  components: {
    Header,
    Team,
    Physical,
    Digital,
    PhotoMarketing,
    Item,
    Footer
  },
  data (){
    return{
      timeline: null,
      info: null,
      loading: true,
      errored: false,
      title: '',
      issaved: false,
      projects:[
        {
          id: 1,
          title: "ChyFood",
          type: 'video',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/he.mp4",
        },
        {
          id: 2,
          title: "Arte Impreso",
          type: 'image',
          category: "Branding, Diseño Web, Fotografía",
          src: "/assets/components/projects/highlight/artim.png",
        },{
          id: 3,
          title: "Say",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/saycommunity.png",
        },{
          id: 4,
          title: "AFE",
          type: 'video',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/highlight/afe.mp4",
        },{
          id: 5,
          title: "Retratos",
          type: 'image',
          category: "Fotografía Profesional",
          src: "/assets/components/projects/highlight/c.png",
        },{
          id: 6,
          title: "Asesorías CGV",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/asesoriascgv.png",
        },{
          id: 7,
          title: "Federación Chilena de Taekwondo",
          type: 'image',
          category: "Estampado de Poleras",
          src: "/assets/components/projects/highlight/shirts.png",
        },{
          id: 8,
          title: "Snog",
          type: 'image',
          category: "LookBook",
          src: "/assets/components/projects/highlight/b.png",
        }
      ]
    }
  },
  mounted(){

    axios
    .get('https://api.sayrin.cl/api/projects')
    .then(response => (this.info = response.data))
    .catch(error => {
        console.log(error)
        this.errored = true
      })
      .finally(() => this.loading = false)

    this. $nextTick(function () {

      const { animation } = this.$refs
      const { text } = this.$refs
      const { pageloader } = this.$refs

      this.timeline = new TimelineLite({

      })



      this.timeline.fromTo(
        animation ,
        1,
        {scaleX: 1},
        {scaleX: 0, ease: Power4.easeInOut}
      )

        this.timeline.fromTo(
          text,
          1,
          {x: 100},
          {x: 150, ease: Power4.easeInOut}, 1
        )

    })
    },
    methods: {
      postNow: function() {

      axios
      .post('https://api.sayrin.cl/api/projects', {
        'title': this.title
      })
      .then(() => this.issaved = true)
      .catch(error => this.issaved = false)

    }
    }
}
</script>

<style lang="scss" scoped>

.animation-container{
  height: 500px;
  position: relative;
}

#animation{
  height: 500px;
  width: 100%;
  background: #212121;
  transform-origin: right;
  position: absolute;
  top: 0;
  left: 0;
}

#pageloader{
  width: 100%;
  height: 100vh;
  background: #212121;
  position: fixed;
   bottom: 0;
   left: 0;
   transform-origin: bottom;
}

</style>
