<template>
  <q-page class="container flex column flex-center justify-around">
    <h4 class="title q-ma-sm text-center">{{ phrases[index] }}</h4>
    <q-img
      src="../assets/vector.png"
      spinner-color="white"
      style="height: auto; width: 230px"
    />

    <div class="flex justify-around full-width">
      <q-btn
        class="button"
        @click="randomPosition"
        rounded
        outline
        label="skip"
      />
      <q-btn
        class="button"
        @click="randomPosition"
        rounded
        label="Gerar Frases"
      />
    </div>
  </q-page>
</template>

<script>
export default {
  name: "PhraseOfDay",
  data() {
    return {
      phrases: [
        "Enfrente os problemas e leve a melhor!",
        "Dê mais atenção ao que você tem de bom na sua vida",
        "Para chegar ao topo, o que importa é começar!",
        "De nada adianta ter sonhos, se você não se empenhar em correr atrás",
        "Preste atenção nas oportunidades que estão à sua frente!",
      ],
      index: null,
    };
  },
  methods: {
    randomPosition() {
      let index = parseInt(Math.random() * 5 + 0);
      this.index = index;
    },
  },
  beforeMount() {
    this.randomPosition();
  },
};
</script>

<style lang="stylus" scoped>
.container {
  background-color: #f95179;
}

.title {
  color: #fff;
}

.button {
  color: #fff;
  height: 50px;
  background-color: #262525;
}
</style>
