<template>

<div class="header margin-top-nav uk-background-cover uk-background-image@l" uk-img data-src="/header.jpeg">

<div class="uk-container say-container-medium">


<div class="uk-child-width-1-2@l uk-flex uk-flex-middle" uk-grid>
  <div>
    <div class="uk-section uk-section-large uk-text-left@l uk-text-center">
          <div class="uk-section uk-section-small">
            <h1 class="responsive">Imagina, Expresa & Crea</h1>
            <h1 class="responsive uk-visible@m accent-secondary">Sayrin, Agencia Digital</h1>
            <p class="uk-width-large@s uk-margin uk-visible@l">Somos una agencia digital dedicada al diseño de productos digitales pensada en innovar el mercado chileno.</p>
            <p class="uk-width-large@s uk-margin-auto uk-margin-top uk-hidden@l">Somos una agencia digital dedicada al diseño de productos digitales pensada en innovar el mercado chileno.</p>
          </div>

          <div class="uk-margin">
            <a uk-scroll href="#selectedprojects" class="uk-button uk-button-large uk-margin-right style-a"> <span class="uk-margin-small-right" uk-icon="icon: arrow-down"></span> Más Información</a>
            <router-link  class="uk-button uk-button-large uk-button-text style-b uk-visible@s" to="/team">Say Team</router-link>
          </div>

    </div>
  </div>
  <div>
    <div class="min-viewport uk-visible@l">
          <section></section>
    </div>
  </div>
</div>

</div>

<div class="uk-position-center-right rotated-text uk-hidden">
  <p class="">¿Frutas? Si ¿Quién no ama las frutas?</p>
</div>

</div>

</template>

<script>

export default {
  name: 'Header',
}

</script>
