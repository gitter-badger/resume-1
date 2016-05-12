<style lang='scss' scope>
  @import '~semantic-ui/dist/semantic.css';

  #app {
    height: 100%;
    margin: 0;
    background-color: #f3f4f5;
  }
  #profile {
    margin-left: auto;
  }
</style>

<script>
  import store from '../core/store'

  export default {
    store,
    ready () {
      this.$http({
        url: 'https://raw.githubusercontent.com/amowu/resume/gh-pages/resume.json',
        method: 'GET'
      }).then(response => {
        console.log(response)
      }, response => {
        console.log(response)
      })
    }
  }
</script>

<template lang='jade'>
  #app.ui.two.column.stackable.grid
    .four.wide.column
      //- TODO: ProfileCard component
      #profile.ui.card
        //- profile avatar
        .image
          img(src='http://www.gravatar.com/avatar/778858b33950746e7049bfc33e94ac50?s=350')
        //- profile info
        .content
          .header Amo Wu
          .meta Front-End Engineer
          .description F2E formosanus.
          .ui.list
            .item
              i.marker.icon
              .content New Taipei City, Taiwan
            .item
              i.mail.icon
              .content
                a(href='mailto:amo260@gmail.com') amo260@gmail.com
            .item
              i.linkify.icon
              .content
                a(href='http://amowu.com') amowu.com
            .item
              i.write.icon
              .content
                a(href='http://blog.amowu.com') blog.amowu.com
            .item
              i.world.icon
              .content Chinese, English, Japanese
        //- social media
        .content
          a.ui.circular.basic.icon.button(href='https://www.linkedin.com/in/amowu', target='_black')
            i.linkedin.icon
          a.ui.circular.basic.icon.button(href='https://github.com/amowu', target='_black')
            i.icon.github
          a.ui.circular.basic.icon.button(href='https://twitter.com/amo_wu', target='_black')
            i.twitter.icon
          a.ui.circular.basic.icon.button(href='https://www.behance.net/amo_wu', target='_black')
            i.icon.behance
    .twelve.wide.column
      router-view
</template>
