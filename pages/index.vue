<script lang="ts" setup>
import { ref } from 'vue'

const content = {
  image: "/images/5851e722a5cf496eb2b780784e4917bc.jpg",
}
const infoPokemon = ref()

const getPokemonData = async () => {
  let randomNumber = Math.floor(Math.random() * 1160) + 1;

  const { data: response } = await useFetch("https://pokeapi.co/api/v2/pokemon/" + randomNumber, {
    method: "GET",
  });
  infoPokemon.value = response.value;
};

const data = ref('')
const dataId = ref()
const dataName = ref()
const dataTypes = ref()
const dataImage = ref()

const getNewData = async function fetchData() {
  let randomNumber = Math.floor(Math.random() * 150) + 1;
  const response = await fetch('https://pokeapi.co/api/v2/pokemon/' + randomNumber)
  const jsonData = await response.json()
  data.value = jsonData; // Almacena el JSON completo en la variable reactiva 'data'
  dataId.value = jsonData.id;
  dataName.value = jsonData.name;
  dataTypes.value = jsonData.types;
  dataImage.value = jsonData.sprites?.front_default;
}

const isLoading = ref(true);
setTimeout(() => {
  getNewData()
  isLoading.value = false;
}, 500);

</script>

<template>
  <NavBar />
  <div class="bg-casper-500">
    <div class="mx-auto max-w-full lg:p-20 sm:p-4">
      <section class="home" id="home">
        <div class="grid lg:grid-cols-4 sm:grid-col-1 gap-4 font-mono">
          <div class="lg:col-start-1 lg:col-span-2 sm:col-start-1 sm:col-span-1">
            <UCard :ui="{
              base: 'overflow-hidden', body: { base: '', padding: 'lg:px-4 lg:py-5 sm:p-2', shadow: 'xl' },
              ring: '', background: 'bg-gradient-to-r from-green-400/20 to-blue-500/40'
            }">
              <div class="lg:px-20 sm:px-10 ">
                <div class="lg:text-5xl sm:text-3xl font-bold lg:px-20 sm:px-10 text-justify flex justify-center">Soy Carlos Moraga</div>
                <!-- <div class="text-3xl font-light flex justify-center p-5">Soy Carlos Moraga</div> -->
                <div class="lg:text-2xl sm:text-xl font-light text-justify p-5">
                  Un apasionado por el desarrollado web, busco
                  constantemente oportunidades para ampliar mis
                  conocimientos, ya que es la clave para alcanzar el éxito
                  en el área del desarrollo.
                  Mi objetivo es encontrar un entorno laboral que no solo
                  me brinde la posibilidad de crecer profesionalmente, sino
                  también de enriquecerme como persona.
                  <br />
                </div>
              </div>
            </UCard>
            <div class="lg:mx-15 lg:my-15 sm:mx-10 sm:my-10">
              <div class="p-5 flex justify-center">
                <form class="parent" action="/pdf/Carlos-Moraga-Vergara.pdf" target="_blank">
                  <button class="custom-button">
                    <span>Descargar CV</span></button>
                </form>
              </div>
              <div class="pt-5 flex justify-center space-x-5">
                <NuxtLink to="https://github.com/CarlosMoragaDev" target="_blank"
                  class="transition duration-150 ease-in-out">
                  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"
                    class="animate-bounce">
                    <path fill="currentColor"
                      d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33c.85 0 1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2" />
                  </svg>
                </NuxtLink>
                <NuxtLink to="https://www.linkedin.com/in/carlos-moraga-vergara/" target="_blank">
                  <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 256 256"
                    class="animate-bounce">
                    <g fill="none">
                      <rect width="256" height="256" fill="#fff" rx="60" />
                      <rect width="256" height="256" fill="#0A66C2" rx="60" />
                      <path fill="#fff"
                        d="M184.715 217.685h29.27a4 4 0 0 0 4-3.999l.015-61.842c0-32.323-6.965-57.168-44.738-57.168c-14.359-.534-27.9 6.868-35.207 19.228a.32.32 0 0 1-.595-.161V101.66a4 4 0 0 0-4-4h-27.777a4 4 0 0 0-4 4v112.02a4 4 0 0 0 4 4h29.268a4 4 0 0 0 4-4v-55.373c0-15.657 2.97-30.82 22.381-30.82c19.135 0 19.383 17.916 19.383 31.834v54.364a4 4 0 0 0 4 4M38 59.628c0 11.864 9.767 21.626 21.632 21.626c11.862-.001 21.623-9.769 21.623-21.631C81.253 47.761 71.491 38 59.628 38C47.762 38 38 47.763 38 59.627m6.959 158.058h29.307a4 4 0 0 0 4-4V101.66a4 4 0 0 0-4-4H44.959a4 4 0 0 0-4 4v112.025a4 4 0 0 0 4 4" />
                    </g>
                  </svg>
                </NuxtLink>
              </div>
            </div>
          </div>
          <div class="lg:col-start-3 lg:col-span-2 sm:col-start-1 sm:col-span-1">
            <UCard
              :ui="{ base: 'overflow-hidden', body: { base: '', padding: 'px-4 py-5 sm:p-2' }, ring: '', divide: '' }"
              class="h-4/5 bg-inherint">
              <div>
                <img :src="content?.image" alt="bg1" />
              </div>
            </UCard>
          </div>
        </div>
      </section>
      <UProgress animation="swing" class="py-8" color="rose" />
      <section class="about" id="about">
        <UCard :ui="{
          base: 'overflow-hidden', body: { base: '', padding: 'lg:px-4 lg:py-5 sm:p-2', shadow: 'xl' },
          ring: '', background: 'bg-gradient-to-r from-blue-500/40 to-green-400/20'
        }">
          <div class="font-mono">
            <h2 class="lg:text-5xl sm:text-3xl font-bold lg:px-20 sm:px-10 text-justify flex justify-center">Perfil</h2>
            <div class="lg:text-2xl sm:text-xl font-light text-justify p-5">
              <p class="lg:text-2xl sm:text-xl font-light text-justify p-5">El año 2014 me titulé de Traductor e
                Intérprete Inglés-Español en la Universidad de las Américas. Mientras que el año 2023, me titulé de la
                carrera Analista Progrmador en el Instituto Profesional Santo Tomás.</p>
              <p class="lg:text-2xl sm:text-xl font-light text-justify p-5">Como Analista Programador he trabajado en
                proyectos utilizando Laravel para desarrollar el entorno de Backend y para Frontend el framework
                Vue 3 y Nuxt 3. También he implementado en proyectos herramientas de trabajo como WebPay y Pinia para
                almacenamiento, librerías de diseño
                como Nuxt UI, Vuetify, Ant Design, así como también consumos de API Rest entre proyectos Backend y
                Frontend.</p>
            </div>
          </div>
        </UCard>
      </section>
      <UProgress animation="swing" class="py-8" color="rose" />
      <section class="skills" id="skills">
        <UContainer :ui="{ base: 'mx-auto', 'padding': 'pt-10 sm:px-6 lg:px-8', 'constrained': 'max-w-7xl' }">
          <div class="font-mono">
            <h2 class="lg:text-5xl sm:text-3xl font-bold lg:px-20 sm:px-10 text-justify flex justify-center p-6">
              Herramientas
            </h2>
            <div class="grid grid-cols-2 gap-4 place-content-center lg:text-xl sm:text-lg font-light">
              <UBadge color="emerald" variant="solid" size="lg" label="Javascript" />
              <UBadge color="emerald" variant="solid" size="lg" label="Html 5" />
              <UBadge color="emerald" variant="solid" size="lg" label="CSS" />
              <UBadge color="sky" variant="solid" size="lg" label="Laravel" />
              <UBadge color="sky" variant="solid" size="lg" label="Vue 3" />
              <UBadge color="sky" variant="solid" size="lg" label="Nuxt 3" />
              <UBadge color="amber" variant="solid" size="lg" label="MySql" />
              <UBadge color="amber" variant="solid" size="lg" label="PHP Storm" />
              <UBadge color="amber" variant="solid" size="lg" label="Visual Studio Code" />
              <UBadge color="amber" variant="solid" size="lg" label="Datagrip" />
              <UBadge color="orange" variant="solid" size="lg" label="WebStorm" />
              <UBadge color="orange" variant="solid" size="lg" label="Github" />
              <UBadge color="orange" variant="solid" size="lg" label="Docker" />
            </div>
          </div>
        </UContainer>
      </section>
      <UProgress animation="swing" class="py-8" color="rose" />
      <section class="projects" id="projects">
        <div class="font-mono">
          <h2 class="lg:text-5xl sm:text-3xl font-bold lg:px-20 sm:px-10 text-justify flex justify-center p-6">
            Repositorio de Proyectos
          </h2>
          <div class="grid lg:grid-cols-4 sm:grid-col-1 gap-2 font-mono">
            <div class="lg:col-start-1 lg:col-span-2 sm:col-start-1 sm:col-span-1">
              <div class="grid justify-items-center">
                <div
                  class="p-5 w-80 flex flex-col items-center justify-center text-center rounded-md border-4 border-main-color shadow-xl transition transition border-opacity-0 hover:border-opacity-100 hover:bg-blue-200">
                  <h3 class="lg:text-3xl sm:text-xl font-bold">To-Do-List-Api</h3>
                  <div class="grid justify-items-center p-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 256 264">
                      <path fill="#FF2D20"
                        d="M255.856 59.62c.095.351.144.713.144 1.077v56.568c0 1.478-.79 2.843-2.073 3.578L206.45 148.18v54.18a4.135 4.135 0 0 1-2.062 3.579l-99.108 57.053c-.227.128-.474.21-.722.299c-.093.03-.18.087-.278.113a4.15 4.15 0 0 1-2.114 0c-.114-.03-.217-.093-.325-.134c-.227-.083-.464-.155-.68-.278L2.073 205.938A4.128 4.128 0 0 1 0 202.36V32.656c0-.372.052-.733.144-1.083c.031-.119.103-.227.145-.346c.077-.216.15-.438.263-.639c.077-.134.19-.242.283-.366c.119-.165.227-.335.366-.48c.119-.118.274-.206.408-.309c.15-.124.283-.258.453-.356h.005L51.613.551a4.135 4.135 0 0 1 4.125 0l49.546 28.526h.01c.165.104.305.232.454.351c.134.103.284.196.402.31c.145.149.248.32.371.484c.088.124.207.232.279.366c.118.206.185.423.268.64c.041.118.113.226.144.35c.095.351.144.714.145 1.078V138.65l41.286-23.773V60.692c0-.36.052-.727.145-1.072c.036-.124.103-.232.144-.35c.083-.217.155-.44.268-.64c.077-.134.19-.242.279-.366c.123-.165.226-.335.37-.48c.12-.118.269-.206.403-.309c.155-.124.289-.258.454-.356h.005l49.551-28.526a4.13 4.13 0 0 1 4.125 0l49.546 28.526c.175.103.309.232.464.35c.128.104.278.197.397.31c.144.15.247.32.37.485c.094.124.207.232.28.366c.118.2.185.423.267.64c.047.118.114.226.145.35m-8.115 55.258v-47.04l-17.339 9.981l-23.953 13.792v47.04l41.297-23.773zm-49.546 85.095V152.9l-23.562 13.457l-67.281 38.4v47.514zM8.259 39.796v160.177l90.833 52.294v-47.505L51.64 177.906l-.015-.01l-.02-.01c-.16-.093-.295-.227-.444-.34c-.13-.104-.279-.186-.392-.3l-.01-.015c-.134-.129-.227-.289-.34-.433c-.104-.14-.227-.258-.31-.402l-.005-.016c-.093-.154-.15-.34-.217-.515c-.067-.155-.154-.3-.196-.464v-.005c-.051-.196-.061-.403-.082-.604c-.02-.154-.062-.309-.062-.464V63.57L25.598 49.772l-17.339-9.97zM53.681 8.893L12.399 32.656l41.272 23.762L94.947 32.65L53.671 8.893zm21.468 148.298l23.948-13.786V39.796L81.76 49.778L57.805 63.569v103.608zM202.324 36.935l-41.276 23.762l41.276 23.763l41.271-23.768zm-4.13 54.676l-23.953-13.792l-17.338-9.981v47.04l23.948 13.787l17.344 9.986zm-94.977 106.006l60.543-34.564l30.264-17.272l-41.246-23.747l-47.489 27.34l-43.282 24.918z" />
                    </svg>
                  </div>
                  <div class="bx pt-8 text-6xl text-main-color">
                    <NuxtLink to="https://github.com/CarlosMoragaDev/To-Do-List-Api" target="_blank">
                      <UButton class="text-main-color text-xl font-medium hover:text-red-600" label="Revisar"
                        variant="link" />
                    </NuxtLink>
                  </div>
                </div>
              </div>
              <div class="grid justify-items-center">
              </div>
            </div>
            <div class="lg:col-start-3 lg:col-span-2 sm:col-start-1 sm:col-span-1">
              <div class="grid justify-items-center">
                <div
                  class="p-5 w-80 flex flex-col items-center justify-center text-center rounded-md border-4 border-main-color shadow-xl transition transition border-opacity-0 hover:border-opacity-100 hover:bg-blue-200">
                  <h3 class="lg:text-4xl sm:text-2xl font-bold">To-Do-List</h3>
                  <div class="grid justify-items-center p-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 512 121">
                      <path fill="#00DC82"
                        d="M103.405 120.261h68.52c2.177 0 4.314-.555 6.2-1.61a12.213 12.213 0 0 0 4.536-4.403a11.754 11.754 0 0 0 1.66-6.013c0-2.111-.575-4.185-1.665-6.013l-46.016-77.31a12.215 12.215 0 0 0-4.536-4.402a12.69 12.69 0 0 0-6.198-1.61a12.69 12.69 0 0 0-6.198 1.61a12.214 12.214 0 0 0-4.537 4.402l-11.766 19.78l-23.004-38.68a12.22 12.22 0 0 0-4.539-4.401A12.7 12.7 0 0 0 69.663 0a12.7 12.7 0 0 0-6.199 1.61a12.22 12.22 0 0 0-4.538 4.402l-57.262 96.21A11.737 11.737 0 0 0 0 108.235c0 2.11.571 4.185 1.659 6.013a12.214 12.214 0 0 0 4.537 4.402a12.692 12.692 0 0 0 6.2 1.611h43.01c17.042 0 29.61-7.26 38.257-21.426l20.994-35.268l11.245-18.874l33.75 56.694h-44.995zm-48.7-18.893l-30.016-.007l44.994-75.588l22.45 37.794l-15.031 25.261c-5.743 9.191-12.267 12.54-22.397 12.54" />
                      <path
                        d="M215.04 119.13h20.119V74.115c0-12.881-1.342-25.762-1.342-25.762l1.186 2.641c1.871 4.088 5.77 12.297 10.349 20.149l27.494 47.985h21.594V20.044h-20.252l.002 45.862c.056 12.598 1.339 25.055 1.339 25.055l-1.014-2.296c-1.79-3.986-5.764-12.539-10.386-20.636l-27.63-47.985H215.04zm143.205-71.342v39.068c0 9.059-5.767 15.853-13.949 15.853c-7.644 0-13.01-6.228-13.01-14.863V47.788h-18.642v44.446c0 16.279 9.925 28.028 25.08 28.028c9.255 0 16.765-4.247 20.52-11.041v9.908h18.778V47.788zm73.38 34.255l22.669-34.255H433.77l-12.337 18.826l-12.342-18.826h-20.386l22.669 34.114l-24.411 37.227h19.986l14.616-21.94l14.484 21.94h19.852zm43.627-34.255h-13.011v16.42h13.011v29.017c0 16.562 10.059 25.904 25.618 25.904H512v-16.561h-8.582c-6.035 0-9.525-3.256-9.525-10.192V64.207H512v-16.42h-18.107v-21.09h-18.64z" />
                    </svg>
                  </div>
                  <div class="bx pt-8 text-6xl text-main-color">
                    <NuxtLink to="https://github.com/CarlosMoragaDev/To-Do-List" target="_blank">
                      <UButton class="text-main-color text-xl font-medium hover:text-red-600" label="Revisar"
                        variant="link" />
                    </NuxtLink>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="p-4 grid lg:grid-cols-4 sm:grid-col-1 gap-2 font-mono">
            <div class="lg:col-start-1 lg:col-span-2 sm:col-start-1 sm:col-span-1">
              <div class="grid justify-items-center">
                <div
                  class="p-5 w-80 flex flex-col items-center justify-center text-center rounded-md border-4 border-main-color shadow-xl transition transition border-opacity-0 hover:border-opacity-100 hover:bg-blue-200">
                  <h3 class="lg:text-4xl sm:text-2xl font-bold">Eeveevolution</h3>
                  <div class="grid justify-items-center p-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 24 24">
                      <path fill="currentColor" fill-rule="evenodd"
                        d="M3 12a9 9 0 1 1 18 0a9 9 0 0 1-18 0Zm2.07 1a7.002 7.002 0 0 0 13.86 0h-4.1a3.001 3.001 0 0 1-5.66 0h-4.1Zm13.86-2a7.001 7.001 0 0 0-13.86 0h4.1a3.001 3.001 0 0 1 5.66 0h4.1ZM12 13a1 1 0 1 0 0-2a1 1 0 0 0 0 2Z"
                        clip-rule="evenodd" />
                    </svg>
                  </div>
                  <div class="bx pt-8 text-6xl text-main-color">
                    <NuxtLink to="https://github.com/CarlosMoragaDev/hangman" target="_blank">
                      <UButton class="text-main-color text-xl font-medium hover:text-red-600" label="Revisar"
                        variant="link" />
                    </NuxtLink>
                  </div>
                </div>
              </div>
              <div class="grid justify-items-center">
              </div>
            </div>
            <div class="lg:col-start-3 lg:col-span-2 sm:col-start-1 sm:col-span-1">
              <div class="grid justify-items-center">
                <div
                  class="p-5 w-80 flex flex-col items-center justify-center text-center rounded-md border-4 border-main-color shadow-xl transition transition border-opacity-0 hover:border-opacity-100 hover:bg-blue-200">
                  <h3 class="lg:text-4xl sm:text-2xl font-bold">App del Clima</h3>
                  <div class="grid justify-items-center p-6">
                    <svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 20 20">
                      <path fill="currentColor"
                        d="M14.517 10.016a4.481 4.481 0 0 0-8.908-.707c.46-.037.92-.025 1.377.032c1.351.17 2.604.725 3.769 1.404c.71.415 1.608.533 2.552.403c.399-.056.78-.152 1.128-.273a4.51 4.51 0 0 0 .082-.86Zm-9.44-5.634l-.07-.058a.5.5 0 0 0-.638.765l.858.858l.07.058a.5.5 0 0 0 .638-.765l-.859-.858Zm10.662.637a.5.5 0 0 0-.765-.637l-.859.858l-.058.07a.5.5 0 0 0 .765.637l.859-.858l.058-.07ZM10.52 2.435a.5.5 0 0 0-.992.09v1.213l.008.09a.5.5 0 0 0 .992-.09V2.524l-.008-.09Zm-6.78 9.504c1.056-.576 2.036-.734 2.997-.614c.974.123 1.96.535 3.01 1.148c1.203.701 2.584.829 3.834.656c1.248-.173 2.41-.651 3.21-1.222a.5.5 0 0 0-.582-.814c-.658.47-1.666.893-2.765 1.045c-1.097.152-2.236.03-3.193-.529c-1.108-.646-2.227-1.13-3.39-1.276c-1.175-.147-2.365.054-3.6.728a.5.5 0 0 0 .479.878Zm2.997 1.386c-.961-.12-1.941.038-2.997.614a.5.5 0 0 1-.48-.878c1.236-.674 2.426-.875 3.602-.728c1.162.146 2.281.63 3.39 1.276c.956.558 2.095.681 3.192.53c1.098-.153 2.107-.575 2.765-1.046a.5.5 0 0 1 .582.814c-.8.57-1.963 1.049-3.21 1.222c-1.25.173-2.631.045-3.834-.656c-1.05-.613-2.036-1.025-3.01-1.148ZM3.74 15.94c1.056-.576 2.036-.734 2.997-.614c.974.123 1.96.535 3.01 1.148c1.203.701 2.584.829 3.834.656c1.248-.173 2.41-.651 3.21-1.222a.5.5 0 0 0-.582-.814c-.658.47-1.666.893-2.765 1.045c-1.097.152-2.236.03-3.193-.529c-1.108-.646-2.227-1.13-3.39-1.276c-1.175-.147-2.365.054-3.6.728a.5.5 0 0 0 .479.878Z" />
                    </svg>
                  </div>
                  <div class="bx pt-8 text-6xl text-main-color">
                    <NuxtLink to="https://github.com/CarlosMoragaDev/WeatherApp" target="_blank">
                      <UButton class="text-main-color text-xl font-medium hover:text-red-600" label="Revisar"
                        variant="link" />
                    </NuxtLink>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="p-5">
            <div class="grid justify-items-center">
              <div class="p-5 w-80% flex flex-col items-center justify-center text-center rounded-md border-4 border-main-color shadow-xl
                 transition border-opacity-0 hover:border-opacity-100 hover:bg-blue-200">

                <h3 class="lg:text-4xl sm:text-2xl font-bold pb-4">Pokedex</h3>
                <UCard :ui="{
                  base: 'overflow-hidden', header: { background: 'bg-red-600' },
                  body: { base: '', padding: 'lg:px-4 lg:py-5 sm:p-2', shadow: 'xl' },
                  footer: { background: 'bg-red-600' },
                  ring: 'ring-1 ring-gray-200 dark:ring-gray-800',
                }">
                  <template #header>
                    <div class="flex items-center space-x-2">
                      <span class="w-3 h-3 rounded-full bg-blue-500"></span>
                      <span class="w-3 h-3 rounded-full bg-green-500"></span>
                      <span class="w-3 h-3 rounded-full bg-yellow-500"></span>
                    </div>
                  </template>
                  <div v-if="isLoading" class="grid justify-items-center">
                    <UButton size="xl" variant="outline" loading>Cargando</UButton>
                  </div>
                  <div v-else>
                    <div class="flex justify-center">
                      <img class="w-40" :src=dataImage alt="test-pokemon" />
                      <ul>
                        <div class="lg:text-2xl sm:text-xl font-light text-justify capitalize p-5">{{ 'N°: ' +
                          dataId
                        }}
                        </div>
                        <div class="lg:text-2xl sm:text-xl font-light text-justify capitalize p-5">{{ 'Nombre: ' +
                          dataName }}</div>
                        <div v-for="(type, index) in dataTypes" :key="index">
                          <div class="lg:text-2xl sm:text-xl font-light text-justify capitalize p-5">{{
                            'Tipo: ' + type?.type?.name }}
                          </div>
                        </div>
                      </ul>
                    </div>
                  </div>
                  <template #footer>
                    <div class="flex justify-center">
                      <UButton size="lg" color="amber" variant="solid" label="Obten datos de un Pokemon"
                        @click="getNewData" />
                    </div>
                  </template>
                </UCard>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
  <Footer />
</template>

<style scoped>
.custom-button {
  border: 0;
  background-image: linear-gradient(150deg, #9500ff, #09f, #00DDFF);
  border-radius: 8px;
  color: #fff;
  display: flex;
  font-size: 18px;
  padding: 4px;
  cursor: pointer;
  transition: .3s;
}

.custom-button span {
  background-color: #111;
  padding: 16px 24px;
  border-radius: 6px;
  transition: .3s;
}

.custom-button:hover span {
  background: none;
}

.custom-button:active {
  transform: scale(0.9);
}
</style>
