<template>
  <div class="bg-trueGray-800 min-h-screen max-h-full text-white">
    
    <!-- Navbar -->
    <Header
      :LoadingStateProps = "loadingState ? true : false"
      @loading-state = "loadingState = !loadingState"
    />
    <!-- End Navbar -->
    
    <!-- Loading State -->
      <main v-if="loadingState == true" class="pb-5 max-w-[90rem] mx-auto animate-pulse">
      
      <!-- Streaming Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3">

        <!-- Stream -->
        <div class="col-span-2">

          <!-- Stream Skeleton -->
          <div class="w-full h-[200px] md:h-[400px] lg:h-full bg-trueGray-600" />
          <!-- End Stream Skeleton -->

        </div>
        <!-- End Stream -->

        <!-- Episodes Desktop version -->
        <div class="hidden lg:block">
          <p class="text-center font-bold text-lg cursor-default">Episodes</p>

          <!-- Episodes Skeleton -->
          <div class="mt-3 overflow-y-auto h-[480px]">

            <!-- Episode -->
            <div class="flex flex-col items-start space-y-5">
              <div class="mx-3 space-y-1">
                <div class="w-[200px] h-6 bg-trueGray-600 rounded-full"></div>
                <div class="w-[180px] h-4 bg-trueGray-600 rounded-full"></div>
              </div>
            </div>
            <!-- End Episode -->

          </div>
          <!-- End Episodes Skeleton -->
          
        </div>
        <!-- End Episodes Desktop version -->

      </section>
      <!-- End Streaming Section -->

      <!-- Info Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3 mb-4 mt-2 mx-5 space-y-2">

          <!-- Title & Info Skeleton -->
          <div class="col-span-2">
            <div class="w-[300px] md:w-[600px] lg:w-[700px] h-6 bg-trueGray-600 rounded-full"></div>
            <div class="w-[150px] md:w-[300px] lg:w-[400px] h-4 bg-trueGray-600 rounded-full my-2"></div>
          </div>
          <!-- End Title & Info Skeleton -->

          <!-- Server List Skeleton -->
          <div class="col-span-2">
            <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-4">

              <!-- Server -->
              <div v-for="loop in 5" :key="loop" class="p-2 md:px-5 bg-trueGray-600 text-trueGray-600 text-opacity-0 rounded-lg text-center font-semibold cursor-default"> <p class="bg-trueGray-500 rounded-lg">Indonesia 360p</p></div>
              <!-- End Server -->

            </div>
          </div>
          <!-- End Server List Skeleton -->

      </section>
      <!-- End info Section -->

      <!-- Episodes Section Ipad & Mobile -->
      <section class="lg:hidden grid grid-cols-1 mb-4 mt-2 mx-5 space-y-2">
        <div class="w-full border-b-2 border-trueGray-700" />
        <p class="font-bold text-lg cursor-default">Episodes</p>

        <!-- Episodes Skeleton -->
        <div v-show="loadingState == true" class="mt-3 overflow-y-auto h-[280px] bg-trueGray-600 rounded-lg divide-y-2 divide-trueGray-700">
          <div class="flex flex-col items-start p-3 hover:bg-black duration-150 space-y-4">

            <!-- Episode -->
            <div v-for="loop in 3" :key="loop" class="mx-3 animate-pulse space-y-1">
              <div class="w-[200px] h-6 bg-trueGray-500 rounded-full animate-pulse"></div>
              <div class="w-[180px] h-4 bg-trueGray-500 rounded-full animate-pulse"></div>
            </div>
            <!-- Episode -->

          </div>
        </div>
        <!-- End Episodes Skeleton -->
      </section>
      <!-- End Episodes Section Ipad & Mobile -->

      <!-- Recommended Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3 mb-4 mt-2 mx-5 space-y-2">
        <div class="col-span-2 space-y-2">
          <div class="w-full border-b-2 border-trueGray-700" />
          <p class="text-xl font-bold cursor-default">Recommended</p>
        </div>

        <!-- Anime Cards Skeleton -->
        <div class="col-span-2 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3">
          <AnimeCardSkeleton />
        </div>
        <!-- End Anime Cards Skeleton -->

      </section>
      <!-- End Recommended Section -->

      </main>
    <!-- End Loading State -->

    <!-- Data State -->
      <main v-else class="pb-5 max-w-[90rem] mx-auto">
        
      <!-- Streaming Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3">

        <!-- Stream -->
        <div class="col-span-2">

          <!-- Stream Container -->
          <img src="../../assets/images/myponyasia/landscape1.png" class="w-full h-full">
          <!-- End Stream Container -->

        </div>
        <!-- End Stream -->

        <!-- Episodes Desktop version -->
        <div class="hidden lg:block">
          <p class="text-center font-bold text-lg cursor-default">Episodes</p>

          <!-- Episodes -->
          <div class="mt-3 overflow-y-auto h-[480px]">

            <!-- Episode -->
            <a v-for="loop in 15" :key="loop" href="#" class="flex flex-col items-start p-3 hover:bg-black duration-150">
              <div class="mx-3">
              <p class="text-lg font-semibold">Episode 1</p>
              <p class="text-xs"> 12-Juni-2021 </p>
              </div>
            </a>
            <!-- End Episode -->

          </div>
          <!-- End Episodes -->

        </div>
        <!-- End Episodes Desktop version -->

      </section>
      <!-- End Streaming Section -->

      <!-- Info Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3 mb-4 mt-2 mx-5 space-y-2">

          <!-- Title & Info -->
          <div class="col-span-2 space-y-2">
            <p class="font-bold text-base md:text-xl">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Necessitatibus, aut aperiam amet voluptas vel sed ullam qui dignissimos impedit illum.</p>
            <p class="font-semibold text-sm md:text-base"> Episode 14 • 16 july 2021</p>
          </div>
          <!-- End Title & Info -->

          <!-- Server List -->
          <div class="col-span-2">
            <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-4">

              <!-- Server -->
              <a v-for="loop in 10" :key="loop" href="#" class="p-2 px-2 md:px-5 bg-trueGray-600 hover:bg-blue-700 duration-150 rounded-lg text-center font-semibold">Indonesia 360p</a>
              <!-- End Server -->

            </div>
          </div>
          <!-- End Server List -->

      </section>
      <!-- End Info Section -->

      <!-- Episodes Section Ipad & Mobile -->
      <section class="lg:hidden grid grid-cols-1 mb-4 mt-2 mx-5 space-y-2">
        <div class="w-full border-b-2 border-trueGray-700" />
        <p class="font-bold text-lg cursor-default">Episodes</p>

        <!-- Episodes -->
        <div class="mt-3 overflow-y-auto h-[280px] bg-trueGray-600 rounded-lg divide-y-2 divide-trueGray-700">

          <!-- Episode -->
          <a v-for="loop in 10" :key="loop" href="#" class="flex flex-col items-start p-3 hover:bg-black duration-150">
            <div class="mx-1.5">
            <p class="text-lg font-semibold">Episode 1</p>
            <p class="text-xs"> 12-Juni-2021 </p>
            </div>
          </a>
          <!-- End Episode -->

        </div>
        <!-- End Episodes -->

      </section>
      <!-- End Episodes Section Ipad & Mobile -->

      <!-- Recommended Section -->
      <section class="grid grid-cols-2 lg:grid-cols-3 mb-4 mt-2 mx-5 space-y-2">
        <div class="col-span-2 space-y-2">
          <div class="w-full border-b-2 border-trueGray-700" />
          <p class="text-xl font-bold cursor-default">Recommended</p>
        </div>

        <!-- Anime Cards -->
        <div class="col-span-2 grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3">
          <AnimeCard />
        </div>
        <!-- End Anime Cards -->

      </section>
      <!-- End Recommended Section -->

      </main>
    <!-- End Data State -->

    <!-- Footer -->
    <Footer />
    <!-- End Footer -->

  </div>
</template>

<script>
import {ref} from 'vue'
import Header from '../../components/mpa/Header.vue'
import Footer from '../../components/mpa/Footer.vue'
import AnimeCard from '../../components/mpa/parts/AnimeCard.vue'
import AnimeCardSkeleton from '../../components/mpa/parts/AnimeCardSkeleton.vue'

export default {

  props: {
    loadingStateProps: {
      type: Boolean,
      default: false,
    }
  },

  components:{
    Header,
    Footer,
    AnimeCard,
    AnimeCardSkeleton,
  },

  setup(){

    const loadingState = ref(false)


    return{
      loadingState,
    }
  }
}
</script>