<template>
<div>
  <Header></Header>

  <section class="uk-section" v-if="errored">
      <div class="uk-container tm-container-medium">
        <p>We're sorry, we're not able to retrieve this information at the moment, please try back later</p>
      </div>
    </section>

  <div v-else class="uk-section">
    <div class="uk-container say-container-medium">
        <div v-if="loading">Cargando...</div>
        <div>{{ info }}</div>
    </div>
  </div>

  <div class="uk-section">
    <div class="uk-container say-container-medium">
      <h3>Agregar Nuevo Proyecto</h3>
      <form  method="post" @submit.prevent="postNow">
      <p>
        <label for="name">Name: {{title}}</label>
        <input type="text" name="name" id="name" v-model="title">
      </p>

      <!--<p>
        <label for="description">Description: {{description}}</label>
        <input type="text" name="description" id="description" v-model="description">
      </p>-->

      <p>
        <input type="submit" value="Submit">
      </p>
    </form>
    <div v-if="issaved">Guardado Satisfactoriamente</div>
    </div>
  </div>

  <div class="uk-section">

    <div class="uk-container say-container-medium">

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
       <p class="uk-width-large@s uk-margin">
         Somos una agencia digital dedicada al diseño de productos digitales pensada en innovar el mercado chileno.
       </p>
     </div>

   </div>
  </div>

  <div class="uk-section">
    <div class="uk-container say-container-medium">
      <div class="uk-child-width-1-3@l uk-child-width-1-2@m uk-child-width-1-1 " uk-grid>
        <div>
          <div>
            <h2>Imagina</h2>
            <p class="uk-margin">Lorem ipsum convallis morbi facilisis curabitur nisl gravida dolor posuere, nibh gravida lectus magna metus nec adipiscing nullam donec, aliquam praesent est consectetur gravida nam ante elementum class porta elit nibh vehicula convallis nisi curabitur</p>
            <a href="" class="uk-button uk-button-large style-a">Let's go</a>
          </div>
        </div>
        <div>
          <div>
            <h2>Expresa</h2>
            <p class="uk-margin">Donec dui taciti euismod leo volutpat enim erat etiam et maecenas consequat risus volutpat ultrices, quis accumsan gravida risus vestibulum turpis dapibus elementum vestibulum lorem vulputate viverra lectus duis mattis tristique curabitur taciti et.</p>
            <a href="" class="uk-button uk-button-large style-a">Let's go</a>
          </div>
        </div>
        <div>
          <div>
            <h2>Crea</h2>
            <p class="uk-margin">Id litora sapien nisl ipsum taciti rutrum justo, aliquam curabitur cubilia fusce convallis quis, ornare lectus commodo taciti bibendum convallis sodales ipsum porta rhoncus lacinia ipsum aptent sodales platea.</p>
            <a href="" class="uk-button uk-button-large style-a">Let's go</a>
          </div>
        </div>
      </div>
    </div>
  </div>


<Digital></Digital>
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

</div>

<div id="pageloader" ref="pageloader"></div>

</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/home/Header.vue'
import Team from '@/components/home/Team.vue'
import Physical from '@/components/home/Physical.vue'
import Digital from '@/components/home/Digital.vue'
import PhotoMarketing from '@/components/home/PhotoMarketing.vue'
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
    Item
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
          title: "Poleras Corporativas",
          type: 'image',
          category: "Artículos Corporativos",
          src: "/assets/components/projects/highlight/shirts.png",
        },{
          id: 6,
          title: "Asesorías CGV",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/asesoriascgv.png",
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
        pageloader,
        2,
        {scaleY: 1},
        {scaleY: 0, ease: Power4.easeInOut}
      )

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
