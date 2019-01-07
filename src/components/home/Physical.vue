<template>

  <div class="uk-section">
    <div class="uk-container uk-container-large">
      <div  uk-grid>
      <div class="uk-width-2-5@m">
          <div class="uk-section uk-section-large" uk-sticky="bottom: true" >

              <div class=" uk-width-large@s">
                <h1 class="responsive-small">Artículos Publicitarios</h1>
                <h1 class="responsive-small accent-secondary margin-bottom">Crea</h1>
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
      <div class="uk-width-3-5@m">
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
  name: 'physical',
  components: {
    Item
  },
  data (){
    return{
      projects:[
       {
          id: 11,
          title: "Poleras Corporativas",
          type: 'image',
          category: "Artículos Corporativos",
          src: "/assets/components/projects/highlight/shirts.png",
        },
        {
           id: 12,
           title: "Sayrin",
           type: 'image',
           category: "Artículos Corporativos",
           src: "/assets/components/projects/physical/paper.png",
         }
      ]
    }
  }
}
</script>

<style lang="css">
</style>
