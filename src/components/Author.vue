<template>
  <div class="author">
    <g-link to="/">
      <g-image
        alt="Author image"
        class="author__image"
        src="~/assets/images/author.jpg"
        width="180"
        height="180"
        blur="5"
      />
    </g-link>

    <h1 v-if="showTitle" class="author__site-title">
      {{ $static.metadata.siteName }}
    </h1>

    <p class="author__intro">
      你终于来啦
    </p>

    <p class="author__links">
      <g-link href="https://travellings.now.sh/" title="开往" target="_blank"
        ><font-awesome :icon="['fas', 'plane']"
      /></g-link>
      <!--<g-link
        href="//blog.jalenchuh.cn/atom.xml"
        title="RSS 订阅"
        target="_blank"
        style="color: #F5A623;"
        ><font-awesome :icon="['fas', 'rss']"/></g-link
      >--><g-link to="/archives" title="归档" style="color: var(--title-color);"
        ><font-awesome :icon="['fas', 'archive']"/></g-link
      ><g-link to="/friends" title="友链" style="color: #06a878;"
        ><font-awesome :icon="['fas', 'user-friends']"/></g-link
      ><g-link to="/about" title="关于" style="color: #117cb7"
        ><font-awesome :icon="['fas', 'id-badge']"
      /></g-link>
    </p>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  props: ["showTitle"]
};
</script>

<style lang="stylus">
.author
  margin 0 auto
  max-width 500px
  text-align center
  padding calc(var(--space) / 2) 0

  &__image
    border-radius 100%
    width 90px
    height 90px
    margin-bottom 1em

  &__intro
    opacity 0.8

  &__site-title
    font-size 1.5em

  &__links
    margin-top -0.5em
    font-size 1em

    a
      color var(--main-color)
      margin 0 0.5em
</style>
