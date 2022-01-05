<template>
  <span :class="type">{{ type }}</span>
</template>

<script>
export default {
  name: "Type",
  props: {
    type: String,
  },
};
</script>

<style scoped>
.normal {
  background-color: #a9ac99 !important;
}
.fire {
  background-color: #ff001d !important;
}
.water {
  background-color: #008bff !important;
}
.electric {
  background-color: #ffd129 !important;
}
.grass {
  background-color: #15db51 !important;
}
.ice {
  background-color: #1bcbff !important;
}
.fighting {
  background-color: #d8625f !important;
}
.poison {
  background-color: #bf339a !important;
}
.ground {
  background-color: #e3c051 !important;
}
.flying {
  background-color: #8f86ff !important;
}
.psychic {
  background-color: #ff0099 !important;
}
.bug {
  background-color: #9cc616 !important;
}
.rock {
  background-color: #bdaf64 !important;
}
.ghost {
  background-color: #7053bc !important;
}
.dragon {
  background-color: #8b35f0 !important;
}
.dark {
  background-color: #382c28 !important;
}
.steel {
  background-color: #aba8bb !important;
}
.fairy {
  background-color: #ff7bef !important;
}
span {
  display: inline-block;
  width: 66px;
  margin-bottom: 4px;
  background: #dbdbdb;
  border: 1px solid #a3a3a3;
  border-radius: 4px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  color: #fff;
  font-size: 0.75rem;
  font-weight: normal;
  line-height: 1.5rem;
  text-align: center;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.7);
  text-transform: uppercase;
  transition: opacity 0.4s;
}
</style>
