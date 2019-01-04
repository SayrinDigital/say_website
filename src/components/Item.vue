<template>

  <div>
    <div class="project-card">
      <a class="uk-display-block" href="">
        <div>
          <div v-if="item.type === 'image'">
            <img  v-bind:src="item.src" uk-img alt="">
          </div>
            <div v-if="item.type === 'video'">
              <video  loop muted playsinline uk-video="autoplay: inview">
              <source v-bind:src="item.src" type="video/mp4">
              </video>
            </div>
          <div class="uk-margin uk-text-center">
            <h4>{{ item.title }}</h4>
            <p>{{ item.category }}</p>
          </div>
        </div>
      </a>
    </div>
  </div>

</template>

<script>
export default {
  name: 'item',
  props: ['item']
}
</script>

<style lang="css">
</style>
