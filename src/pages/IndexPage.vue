<template>
  <q-page class="flex column flex-center">
    <h5 class="text-center q-px-md">{{ phrases[phraseIndex] }}</h5>
    <q-btn icon="autorenew" label="Stacked" stack glossy color="purple" @click="randomPosition" />
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
