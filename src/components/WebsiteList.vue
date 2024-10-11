
<template>
    <v-row class="sitelist">
      <v-col
        v-for="(image, index) in images"
        :key="index"
        class="d-flex child-flex"
        cols="3"
      >
        <v-hover v-slot:default="{ isHovering }">
          <a :href="image.link" target="_blank" rel="noopener noreferrer">
            <v-img
              :lazy-src="image.lazySrc"
              :src="image.src"
              aspect-ratio="1"
              class="bg-grey-lighten-2"
              cover
            >
              <template v-slot:placeholder>
                <v-row
                  align="center"
                  class="fill-height ma-0"
                  justify="center"
                >
                  <v-progress-circular
                    color="grey-lighten-5"
                    indeterminate
                  ></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </a>
        </v-hover>
      </v-col>
    </v-row>
  </template>
  
  <script lang="ts" setup>
    // Define the list of images and their corresponding links
    const images = [
    {
        link: 'https://app.offerbox.jp/v2/sindex',
        src: 'https://app.offerbox.jp/v2/assets/img/common/n_logo.png',
        lazySrc: 'https://picsum.photos/10/6?image=15'
      },
      {
        link: 'https://www.onecareer.jp/',
        src: 'https://www.onecareer.jp/_nuxt3/img/logo-thin.png',
        lazySrc: 'https://picsum.photos/10/6?image=15'
      },
      {
        link: 'https://www.gakujo.ne.jp/2026/',
        src: 'https://www.gakujo.ne.jp/2026/assets/svg/site-logo.svg',
        lazySrc: 'https://picsum.photos/10/6?image=15'
      },
      {
        link: 'https://typeshukatsu.jp/',
        src: 'https://typeshukatsu.jp/assets/pc/common/svg/logo-wid-color.svg',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      {
        link: 'https://business.labbase.jp',
        src: 'https://business.labbase.jp/wp-content/themes/business-labbase/img/logo.png.webp',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      {
        link: 'https://www.taiyo-job.co.jp/',
        src: 'https://www.taiyo-job.co.jp/wp-content/themes/taiyojob/images/logo.png',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      {
        link: 'https://acaric.jp/',
        src: '	https://acaric.jp/special/svg/servicelogo_acaric.svg',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      {
        link: 'https://syukatsu-kaigi.jp/',
        src: 'https://static.syukatsu-kaigi.jp/packs/images/student/common/logo_sk-1efb77f7b37cfe132867bca70330703c.svg',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      {
        link: 'https://www.openwork.jp/',
        src: 'https://assets.openwork.jp/images/common/logo_header.svg?01',
        lazySrc: 'https://picsum.photos/10/6?image=20'
      },
      // Add more images and links as needed
    ];
  </script>
<style lang="scss">
.sitelist {
    padding: 20px;
}
  a {
    width: 200px;
    height:120px;
    padding: 0 00px;
    display: block;
    .v-img__img--cover {
        object-fit: contain;
    }
  }
</style>
