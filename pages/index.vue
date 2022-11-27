<script setup>


const tableRows = ref([])
const tableString = ref('')
const loading = ref(false)

// const vatList = computed(()=>{
//   if (!tableString) return [];
//   if (tableString.length < 6) return [];
//   return (tableString || '').split('\n').filter((item) => item.length > 4);
// })

const submit = async () => {}
</script>

<template>
  <VContainer fluid class="fill-height">
    <VRow no-gutters align="center" justify="center" class="fill-height">
      <VCol cols="12" md="4">
        <VRow no-gutters align="center" justify="center">
          <VCol cols="12" class="text-center" align="center" justify="center">
            <h1 class="text-cyan-darken-1 mt-16">Free VIES VAT mass validation tool</h1>

            <VForm class="mt-7 text-center" align="center" justify="center" @submit.prevent="submit">
              <v-textarea label="Paste your VAT codes here (one per line)" v-model="tableString"  rows="3" auto-grow :placeholder="'DE815512007\nHU10962914\nRO17275880'" class="text-area-vies" variant="outlined" color="cyan"
              ></v-textarea>
              <!-- :hint="`${vatList.length} records to validate`"
              persistent-hint -->

              <v-btn
                variant="outlined"
                color="cyan-darken-1"
                :loading="loading"
                prepend-icon="mdi-send"
                @click="validate"
              >
                Validate
              </v-btn>
            </VForm>
            <p class="text-center text-caption mt-10">
              <span>Don't have an account?
                <NuxtLink to="/signup" class="font-weight-bold text-primary">Sign Up</NuxtLink></span>
            </p>
          </VCol>
        </VRow>
      </VCol>
      <VCol v-if="tableRows.length > 0" class="hidden-md-and-down fill-height" cols="12" xs="12">
        <VImg
          src="https://wallpaper.dog/large/5557744.jpg"
          cover
          class="h-100 rounded-xl d-flex align-center justify-center"
        >
          <div class="text-center w-50 text-white mx-auto">
            <h2 class="mb-4">
              Start your journey today
            </h2>
            <p>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Asperiores, inventore quia.
              Dolorum dolores ad ipsum voluptatum rem, hic placeat, odio, odit numquam quod
              veritatis accusantium assumenda! Sequi, provident in! Iure!
            </p>
          </div>
        </VImg>
      </VCol>
    </VRow>
  </VContainer>
</template>

<style>
/* .text-area-vies{
  max-width:400px;
} */
</style>