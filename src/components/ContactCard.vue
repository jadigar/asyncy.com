<template>
  <div class="contact-card">
    <div :class="['picture', type]" />
    <h5 class="is-size-5 has-text-gray-2 has-text-weight-bold">{{ name }}</h5>
    <p class="is-size-6 has-text-gray-3">{{ description }}</p>
    <a-button
      :url="{ href: link, target: undefined }"
      state="primary"
      arrow
      borderless
      outlined
    >{{ btnText }}</a-button>
  </div>
</template>

<script>
export default {
  name: 'ContactCard',
  props: {
    name: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    type: {
      type: String,
      required: true,
      validator: v => ['sales', 'help', 'press'].includes(v)
    },
    link: {
      type: String,
      default: undefined
    }
  },
  computed: {
    btnText: function () { return `Contact ${this.type[0].toUpperCase() + this.type.slice(1)}` }
  }
}
</script>

<style lang="scss">
.contact-card {
  display: block;
  position: relative;
  background-color: $white;
  border-radius: 1rem;
  padding: 2rem;
  box-shadow: 0 4px 27px -16px rgba(0, 0, 0, 0.4);

  .picture {
    margin: 0;
    padding: 0;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center center;
    width: 70px;
    height: 70px;
    margin-bottom: 1.5rem;
    &.sales {
      background-image: url("~@/assets/img/cards/contact/sales.svg");
    }
    &.help {
      background-image: url("~@/assets/img/cards/contact/help.svg");
    }
    &.press {
      background-image: url("~@/assets/img/cards/contact/press.svg");
    }
  }

  h5 {
    padding: 0;
    margin-bottom: 0.5rem;
  }

  p {
    padding: 0;
    height: 80px;
    margin-bottom: 0.75rem;
  }

  button {
    svg {
      position: relative !important;
      width: 20px !important;
      left: unset !important;
      right: unset !important;
      bottom: unset !important;
    }
  }
}
</style>
