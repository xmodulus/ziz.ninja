<template>
  <div>
    <section class="hero is-light is-bold">
      <div class="hero-body">
        <div class="columns">
          <div class="column is-8 is-offset-2">
            <div class="card-content">
              <div class="level">
                <div class="level-left">
                  <img src="../../assets/img/profile.png" class="level-item profile is-hidden-mobile">
                  <h3 class="level-item title">About Me</h3>
                </div>
              </div>
              <div class="content">
              My name is Abdul Aziz. I am currently majoring in Computer Science and Linguistics at the University of Waikato.
              I have been programming and tinkering as a hobby for most of my life, working mostly with PHP and Javascript.
              I enjoy learning languages and hope to work in the field of language processing as it combines my love of both programming and linguistics.
              <br><br>
              📜 Here is my <a class="has-text-weight-bold" href="https://drive.google.com/open?id=1OD-LyXN3m9vAGWvgRnGjnGK73hhvmDUe" @click="clicked(links.resume)">résumé</a> for your perusal.
              </div>
              💌 You may contact me at <a class="has-text-weight-bold" href="mailto:me@ziz.ninja" @click="clicked(links.email)">me@ziz.ninja</a>
              <span class="is-divider"></span>
              <social></social>
              <p-g-p></p-g-p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  import Social from '../partials/social.vue'
  import PGP from '../partials/pgp.vue'
  export default {
    components: {Social, PGP},
    name: 'about',
    data(){
      return {
        links: {
          email: 'email',
          resume: 'resume'
        }
      }
    },
    methods:{
      clicked(label){
        this.$ga.event({
          eventCategory: 'link',
          eventAction: 'linkClick',
          eventLabel: label,
        })
      }
    }
  }
</script>
