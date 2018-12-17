<template>

  <div class="header">
    <div class="">
        <div class="uk-container say-container-medium">

           <div class="uk-flex uk-flex-middle" uk-grid>
             <div class="uk-width-3-5@m">
               <div>

        <div class="uk-position-relative uk-visible-toggle uk-light" uk-slideshow="animation: push; autoplay: true; autoplay-interval: 2000;" >

            <ul class="uk-slideshow-items" uk-height-viewport="min-height: 300">
                <li>
                    <img src="/assets/components/team/c.png" alt="" uk-cover>
                </li>
                <li>
                    <img src="/assets/components/team/b.png" alt="" uk-cover>
                </li>
                <li>
                    <img src="/assets/components/team/a.png" alt="" uk-cover>
                </li>
            </ul>

        </div>
               </div>
             </div>
             <div class="uk-width-2-5@m uk-flex-first@m">
               <div class="uk-section uk-section-large">
                 <div class="uk-width-large@m">
                   <h1 class="responsive">Sayrin, ¿Quién?</h1>
                   <h1 class="responsive accent-secondary">Como en familia</h1>
                   <p>Sayrin nació un día entre la conversación de dos amigos que necesitaban innovar en la actualidad. Crear nuevos productos, nuevas ideas y plasmarlas.</p>
                   <div class="uk-margin">
                     <h3>Seguimos creciendo</h3>
                     <p>Se inició con el desarrollo de productos digitales, tales como sitios web, aplicaciones, diseño. Posteriormente llegamos a la fotografía y la publicidad para así darle un servicio más completo hacia nuestros clientes. Con el tiempo y al notar las necesidades de nuestros clientes al querer un pack completo de servicios que los representen como marca, se inició con la producción de artículos publicitarios.</p>
                   </div>
                   <div class="uk-margin">
                     <h3>Nos preocupamos</h3>
                     <p>Así es como actualmente Sayrin avanza junto a sus clientes, porque tenemos un concepto bastante claro, lo llevamos como en familia, preocupándonos por cada uno de ellos.</p>
                   </div>
                 </div>
               </div>
             </div>
           </div>

        </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'Team'
}
</script>

<style lang="scss">
</style>
