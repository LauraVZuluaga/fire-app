<template>
  <div>
    <b-button id="show-btn" @click="showModal">Rent</b-button>
    <b-modal ref="modalRent" hide-footer title="Pick a date">
      <div class="calendar-container">
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequuntur
          non nobis voluptate iste rem. Cumque modi perferendis alias facilis
          qui, non aspernatur illum maxime autem ex error tempore, eligendi
          odit!
        </p>
        <vc-date-picker
          :value="null"
          color="indigo"
          is-dark
          is-range
        ></vc-date-picker>
      </div>
      <b-button id="show-btn" variant="outline-danger" @click="rent(product.id)"
        >Order</b-button
      >
    </b-modal>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  props: ['product'],
  methods: {
    showModal() {
      this.$refs['modalRent'].show()
    },
    hideModal() {
      this.$refs['modalRent'].hide()
    },
    toggleModal() {
      this.$refs['modalRent'].toggle('#toggle-btn')
    },
    rent(product) {
      this.addItem(product)
      this.$refs.modalRent.hide()
      this.$nuxt.$options.router.push({name: "my-items"})
      console.log(product)
    },
    ...mapMutations(['addItem']),
  },
}
</script>

<style scoped>
button {
  width: 100%;
  border: none;
  padding: 0.5rem;
  color: white;
  font-weight: 700;
  padding: 1rem 4rem;
  border-radius: 100rem;
  background-color: rgb(231, 81, 43);
  color: white;
  font-weight: 700;
  transition: 0.5s;
}
.calendar-container {
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
p {
  color: grey;
}
.text-container {
  padding: 0.5rem;
}
</style>
