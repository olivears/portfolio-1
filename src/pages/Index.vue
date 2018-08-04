<template>
  <q-page>
    <section>
      <div class="bg-grey-3 full-section">
        <banner :data="profession" class="absolute-center banner" />
      </div>
    </section>
    <section>
      <div class="full-section">
        <intro :text="introduction" class="absolute-center intro" />
      </div>
    </section>
    <h3 class="text-center font-courier">/** What I can do for you **/</h3>
    <section>
      <div class="full-section">
        <manifesto :text="manifesto" class="absolute-center manifesto"/>
      </div>
    </section>
    <section>
      <div class="full-section">
        <madskills :skills="skills" class="absolute-center madskills"/>
      </div>
    </section>
    <h3 class="text-center font-courier">/** Stats for nerdz **/</h3>
    <section>
      <div class="full-section">
        <stats :stats="stats" class="absolute-center stats"/>
      </div>
    </section>
    <h3 class="text-center q-pb-xl">/** Work History **/</h3>
    <timeline :data="history" />
  </q-page>
</template>

<style lang="stylus" scoped>
@import '~variables';

.full-section
  position relative
  height 100vh
.banner
  width 100%
.intro
  width 50%
  +respond-max($breakpoint-md)
    width 80%
.manifesto, .madskills
  width 80%
.stats
  width 90%
</style>

<script>
import data from 'statics/data/index.json'
import Banner from 'components/index/Banner'
import Intro from 'components/index/Intro'
import Manifesto from 'components/index/Manifesto'
import Madskills from 'components/index/Madskills'
import Stats from 'components/index/Stats'
import Timeline from 'components/index/Timeline'
export default {
  name: 'PageIndex',
  components: {Banner, Intro, Manifesto, Madskills, Stats, Timeline},
  created () {
    this.introduction = data.introduction
    this.profession = data.profession
    this.manifesto = data.manifesto
    this.skills = data.skills
    this.stats = data.stats
    this.history = data.history
  }
}
</script>