<template>
<div id="app">
  <div >

    <nav id="mainnav" class="uk-navbar-container uk-navbar-transparent" uk-navbar>
      <div class="uk-navbar-left">

        <div class="uk-navbar-item">
          <a href="/">
                    <img style="height: 40px;" src="./assets/logo.svg" class="uk-logo" uk-img="uk-img" alt="">
                  </a>
        </div>

      </div>

      <div class="uk-navbar-right">

        <ul class="uk-navbar-nav uk-visible@s">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/team">Team</router-link></li>
          <li><a href="https://desk.zoho.com/portal/sayrin/home">Soporte</a></li>
          <li><a target="_blank" href="https://accounts.zoho.com/signin?servicename=VirtualOffice&signupurl=https://workplace.zoho.com/orgsignup.do?signup.html">WorkPlace</a></li>
        </ul>

        <div class="uk-navbar-item" >
          <div>

            <div class="link-both-container">
              <a class="  uk-visible@s" target="_blank" href="https://payments.zoho.com/ResellerCustomerSignUp.do?id=1374fd6e1f147813ac5cf9efc7bf364e6d9fe02bfec9392903a812ebb91bba7a&locale=es">Sé Zoho</a>
              <div class="uk-width-large  uk-visible@s" uk-drop="animation: uk-animation-slide-top-small; duration: 500; offset: 40;">
                <div class="uk-card uk-card-body  uk-border-rounded uk-card-default">
                  <div class="uk-child-width-1-2@m uk-drop-grid" uk-grid>
                    <div>
                      <div>
                        <h3>Zoho Workplace</h3>
                        <p>Todas las herramientas que necesites para crear, colaborar y comunicar con tu equipo en una suite de aplicaciones.</p>
                      </div>
                    </div>
                    <div>
                      <div>
                        <h3>Zoho Finances</h3>
                        <p>Crea presupuestos, administra tus clientes, envía recordatorio de pagos automáticos y administra tus gastos.</p>
                      </div>
                    </div>
                  </div>

                  <div class="uk-margin uk-text-center">
                    <a class="button-style-b uk-button-large uk-button " href="/blog">¿Necesitas ayuda?</a>
                  </div>
                </div>
              </div>

              <span class="  uk-visible@s uk-margin-small-right uk-margin-small-left">|</span>

              <a class="">Sé Sayrin</a>
              <div uk-drop="animation: uk-animation-slide-top-small; duration: 500; offset: 40;">
                <div class="uk-card uk-card-body  uk-border-rounded uk-card-default">
                  <div>
                    <div>
                      <div>
                        <h3>Trabajemos Juntos</h3>
                        <p>Completa el siguiente formulario y nos encargaremos te ofrecerte lo mejor para satisfacer tus necesidades.</p>
                      </div>
                    </div>

                    <div class="uk-margin uk-text-center">
                      <a class="button-style-b uk-button-large uk-button " target="_blank" href="/unete">Adelante</a>
                    </div>
                  </div>
                </div>
              </div>
            </div>

          </div>
        </div>


      </div>
    </nav>
  </div>
  <div>
    <router-view/>
  </div>
</div>
</template>

<script>
import UIkit from 'uikit';
import Icons from 'uikit/dist/js/uikit-icons';
UIkit.use(Icons);
export default {
  name: 'app',
};
</script>

<style lang="scss">
@import './assets/css/style.scss';
</style>
