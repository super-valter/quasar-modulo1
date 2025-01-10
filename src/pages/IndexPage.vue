<template>
  <q-page class="flex column flex-center justify-around">
    <q-img
      src="https://www.designi.com.br/images/preview/12831094.jpg"
      spinner-color="white"
      style="max-width: 300px"
    />
    <h4 class="text-center q-px-md color-white">{{ phrases[phraseIndex] }}</h4>
    <q-btn class="button" icon="autorenew" label="Atualizar frase" rounded color="dark" @click="randomPosition" />
  </q-page>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const phrases = [
  'Enfrente os problemas e leve a melhor!',
  'Os presentes de cada dia',
  'Dê mais atenção ao que você tem de bom na sua vida',
  'Não se exija demais',
  'Um passo por dia',
  'Para chegar ao topo, o que importa é começar!',
  'Para hoje, use a roupa da sorte',
  'De nada adianta ter sonhos, se você não se empenhar em correr atrás',
  'Preste atenção nas oportunidades que estão à sua frente!',
  'Positividade para começar o dia é colocar a sua fé em prática'
]
let phraseIndex = ref(0)

const randomPosition = () => {
  phraseIndex.value = Math.floor(Math.random() * phrases.length)
}

onMounted(() => {
  randomPosition()
})
</script>

<style scoped>
.q-page {
  background-color: #f95179;
}
.button {
  width: 90%;
}
</style>
