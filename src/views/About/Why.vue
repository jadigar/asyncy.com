<template>
  <section class="about">
    <div class="container">
      <believing-template
        v-for="(step, idx) of steps"
        :key="`step-${idx}`"
        :idx="idx"
        :name="step.name"
        :content="step.content"
        :blog="step.blog ? step.blog[0] : undefined"
        :blog-url="step.blog ? step.blog[1] : undefined"
        :picture="step.picture"
      />
    </div>
  </section>
</template>

<script>
import PictureOpenSource from '@/assets/img/about-opensource.svg'
import PictureDev from '@/assets/img/about-dev.svg'
import PictureStory from '@/assets/img/about-story.svg'
import BelievingTemplate from '@/components/BelievingTemplate'

export default {
  name: 'Why',
  components: { BelievingTemplate },
  data: () => ({
    steps: [{
      name: 'open source community',
      content: 'Code is brought to life with cross-application metrics and usage insights to empower developers and vendors with actionable data to improve software.',
      picture: PictureOpenSource
    }, {
      name: 'developer',
      content: 'Increasing reusability and reducing complexity by extending the developer journey to create powerful applications; focusing on delivering features more effectively at scale.',
      picture: PictureDev
    }, {
      name: 'story of data',
      content: 'Over the last 50 years we crafted programming languages to communicate with computers. It’s time we amplify this communication with a new language for top-level abstractions that is intuitive and familiar.',
      blog: ['Storytelling your application', '//asyncy.com/blog/story-telling'],
      picture: PictureStory
    }]
  })
}
</script>
