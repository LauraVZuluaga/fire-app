<template>
  <div>
    <div class="container">
      <Hero />
      <LargeCardDisplay
        v-for="cardInfo in largeCardInfo"
        :key="cardInfo.id"
        :cardsSection="cardInfo"
      />
      <SmallCardDisplay
        v-for="smallInfo in smallCardInfo"
        :key="smallInfo.id"
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
