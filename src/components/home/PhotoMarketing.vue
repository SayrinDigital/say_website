<template>

  <div class="uk-section">
    <div class="uk-container uk-container-large">
      <div class="uk-flex"  uk-grid>
      <div class="uk-width-2-5@l">
          <div class="uk-section uk-section-large" uk-sticky="bottom: true" >



              <div class="uk-margin-auto uk-width-large@s">
                <h1 class="responsive-small">Fotografía Profesional</h1>
                <h1 class="responsive-small accent-secondary">Expresa</h1>
                <div class="uk-margin">
                  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
                </div>

              </div>



          </div>
      </div>
      <div class="uk-width-3-5@l uk-flex-first@l">
          <div>
               <div class="uk-section uk-section-large">

                   <div class="uk-child-width-1-2@s"  uk-scrollspy="cls: uk-animation-slide-bottom-medium; target: > div > div; delay: 300;" uk-grid>
                     <Item
                     v-for="project in projects"
                     v-bind:key="project.id"
                     v-bind:item="project"

                     ></Item>
                   </div>

               </div>
          </div>
      </div>
  </div>


</div>
  </div>


</template>

<script>

import Item from '@/components/Item.vue'

export default {
  name: 'photomarketing',
  components: {
    Item
  },
  data (){
    return{
      projects:[
        {
          id: 20,
          title: "ChyFood",
          type: 'image',
          category: "Corporativo",
          src: "/assets/components/projects/photomarketing/a.png",
        },
        {
          id: 21,
          title: "Arte Impreso",
          type: 'image',
          category: "Retrato",
          src: "/assets/components/projects/photomarketing/b.png",
        },{
          id: 22,
          title: "Say",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/photomarketing/c.png",
        },{
          id: 23,
          title: "AFE",
          type: 'image',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/photomarketing/d.png",
        },{
          id: 24,
          title: "AFE",
          type: 'image',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/photomarketing/e.png",
        },{
          id: 25,
          title: "AFE",
          type: 'image',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/photomarketing/f.png",
        }
      ]
    }
  }
}
</script>

<style lang="css">
</style>
