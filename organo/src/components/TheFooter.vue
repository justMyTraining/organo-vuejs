<template>
  <footer class="vc-footer">
    <section class="container d-flex align-items-center  justify-content-between ">
      <ul class="vc-social-medias list-unstyled">
        <li>
          <a href="#">
            <img :src="require('@/assets/images/fb.png')" alt="Facebook">
          </a>
        </li>
        <li>
          <a href="#">
            <img :src="require('@/assets/images/tw.png')" alt="Tweeter">
          </a>
        </li>
        <li>
          <a href="#">
            <img :src="require('@/assets/images/ig.png')" alt="Instagram">
          </a>
        </li>
      </ul>
      <div class="vc-logo">
        <img :src="require('@/assets/images/logo.png')" alt="Organo logo">
      </div>
      <div class="vc-credits">
        Desenvolvido por Alura.
      </div>
    </section>
  </footer>
</template>

<script></script>

<style>
.vc-footer {
  background: url("@/assets/images/fundo.png") center no-repeat #6278F7;
  color: white;
  padding: 75px 0;
}

.vc-social-medias {
  column-gap: 32px;
  display: flex;
}

.vc-credits {
  color: #FFF;
  font-family: Montserrat, sans-serif;
  font-size: 20px;
  font-weight: 500;
}
</style>