<template>
<div class="home">
  <Header></Header>
  <div class="uk-section">

    <div class="uk-container say-container-medium">
      <div class="uk-flex uk-flex-middle uk-grid-medium" uk-grid>
        <div class="uk-width-2-5@m">
          <div>
            <h1 class="responsive">Hey! ¿Sayrin?</h1>
            <h1 class="responsive accent-secondary">Enserio...</h1>
          </div>
        </div>
        <div class="uk-width-3-5@m">
          <div>

            <div>
              <div>
                <p>Oh, hey! Te damos la bienvenida a Sayrin, somos una agencia conformada por un equipo joven creativo que se encarga de brindar la máxima experiencia en cuanto a innovación enfocada en ti y tus clientes. Creamos productos digitales, diseño,
                  contenido, artículos publicitarios, un todo en uno. </p>
              </div>

            </div>

          </div>
        </div>
      </div>
    </div>

  </div>

<Physical></Physical>
<Digital></Digital>

</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/home/Header.vue'
import Team from '@/components/home/Team.vue'
import Physical from '@/components/home/Physical.vue'
import Digital from '@/components/home/Digital.vue'
import PhotoMarketing from '@/components/home/PhotoMarketing.vue'

export default {
  name: 'home',
  components: {
    Header,
    Team,
    Physical,
    Digital,
    PhotoMarketing
  }
}
</script>

<style lang="scss" scoped>


</style>
