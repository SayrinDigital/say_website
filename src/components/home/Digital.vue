<template>

  <div class="uk-section">
    <div class="uk-container uk-container-large">
      <div  uk-grid>
      <div class="uk-width-2-5@l">
          <div class="uk-section uk-section-large" uk-sticky="bottom: true; media: @l" >

              <div class="uk-margin-auto uk-width-large@s">
                <h1 class="responsive-small">Productos Digitales</h1>
                <h1 class="responsive-small accent-secondary margin-bottom">Imagina</h1>
                <div class="uk-margin-medium-bottom">
                  <p>Lorem ipsum dolor sit amet, consectetur, et dolore magna aliqua. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
                </div>
                <ul class="uk-list uk-margin-remove">
                  <li><span class="uk-margin-small-right uk-icon" uk-icon="check"></span> Alignment options for blogs and posts</li>
                  <li><span class="uk-margin-small-right uk-icon" uk-icon="check"></span> Alignment options for blogs and posts</li>
                  <li><span class="uk-margin-small-right uk-icon" uk-icon="check"></span> Alignment options for blogs and posts</li>
                  <li><span class="uk-margin-small-right uk-icon" uk-icon="check"></span> Alignment options for blogs and posts</li>
                </ul>
              </div>

          </div>
      </div>
      <div class="uk-width-3-5@l">
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
  name: 'digital',
  components: {
    Item
  },
  data (){
    return{
      projects:[
        {
          id: 7,
          title: "ChyFood",
          type: 'video',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/he.mp4",
        },
        {
          id: 8,
          title: "Arte Impreso",
          type: 'image',
          category: "Branding, Diseño Web, Fotografía",
          src: "/assets/components/projects/highlight/artim.png",
        },{
          id: 9,
          title: "Say",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/saycommunity.png",
        },{
          id: 10,
          title: "AFE",
          type: 'video',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/highlight/afe.mp4",
        },{
          id: 11,
          title: "Poleras Corporativas",
          type: 'image',
          category: "Artículos Corporativos",
          src: "/assets/components/projects/highlight/shirts.png",
        },{
          id: 12,
          title: "Asesorías CGV",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/asesoriascgv.png",
        },
        {
          id: 13,
          title: "ChyFood",
          type: 'video',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/he.mp4",
        },
        {
          id: 14,
          title: "Arte Impreso",
          type: 'image',
          category: "Branding, Diseño Web, Fotografía",
          src: "/assets/components/projects/highlight/artim.png",
        },{
          id: 15,
          title: "Say",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/saycommunity.png",
        },{
          id: 16,
          title: "AFE",
          type: 'video',
          category: "Fotografía, Bodegón",
          src: "/assets/components/projects/highlight/afe.mp4",
        },{
          id: 17,
          title: "Poleras Corporativas",
          type: 'image',
          category: "Artículos Corporativos",
          src: "/assets/components/projects/highlight/shirts.png",
        },{
          id: 18,
          title: "Asesorías CGV",
          type: 'image',
          category: "Branding, Diseño Web",
          src: "/assets/components/projects/highlight/asesoriascgv.png",
        }
      ]
    }
  }
}
</script>

<style lang="css">
</style>
