<template>
  <div>
    <div class="container">
      <Hero />
      <LargeCardDisplay
        v-for="(cardInfo, i) in largeCardInfo"
        :key="i.id"
        :cardsSection="cardInfo"
      />
      <SmallCardDisplay
        v-for="(smallInfo, i) in smallCardInfo"
        :key="i.id"
        :smallCardSections="smallInfo"
      />
    </div>
  </div>
</template>

<script>
import { largeCardSections } from '@/assets/data.js'
import { smallCardSections } from '@/assets/data.js'
export default {
  name: 'IndexPage',
  data() {
    return {
      largeCardInfo: largeCardSections,
      smallCardInfo: smallCardSections,
    }
  },
}
</script>
