<template>
  <div class="Float">
    <img class="Float__image" src="../assets/icons/whatsapp.svg" alt="">
  </div>
</template>

<style lang="scss">
.Float{
  position: fixed;
  right: 1rem;
  bottom: 1rem;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem;
  background: #00d36f;
  border-radius: 50%;

  &__image{
    display: block;
    width: 3rem;
  }
}
</style>