<template>
  <div>
    <main>
      <section class="absolute w-full h-full">
        <div
          class="absolute top-0 w-full h-full bg-gray-900"
          style="background-size: 100%; background-repeat: no-repeat"
        ></div>
        <div class="container mx-auto px-4 h-full">
          <div class="flex content-center items-center justify-center h-full">
            <div class="w-full lg:w-4/12 px-4">
              <div
                class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded-lg bg-gray-300 border-0"
              >
                <div class="rounded-t mb-0 px-6 py-6">
                  <div class="text-center mb-3">
                    <h3 class="text-gray-600 font-bold">Shuffle</h3>
                  </div>
                  <hr class="mt-6 border-b-1 border-gray-400" >
                </div>
                <div class="flex-auto px-4 lg:px-10 py-10 pt-0">
                  <form @submit="onSubmit">
                    <div class="relative w-full mb-3">
                      <label
                        class="block uppercase text-gray-700 text-xs font-bold mb-2"
                        >Text</label
                      ><input
                        type="text"
                        class="border-0 px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:ring w-full"
                        v-model="text"
                        placeholder="Text"
                        style="transition: all 0.15s ease 0s"
                      >
                    </div>
                    <div>
                      <label
                        class="block uppercase text-gray-700 text-xs font-bold mb-2"
                        >Shuffed Word</label>
                        <input
                        type="text"
                        class="border-0 px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:ring w-full"
                        placeholder="Shuffled Word"
                        :value="shuffledText"
                        style="transition: all 0.15s ease 0s"
                      >
                    </div>
                    <div class="text-center mt-6">
                      <input
                        class="bg-gray-900 text-white active:bg-gray-700 text-sm font-bold uppercase px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1 mb-1 w-full"
                        type="submit"
                        style="transition: all 0.15s ease 0s"
                        value="Shuffle"
                      >
                    </div>
                  </form>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>
<script>
export default {
  name: "Form",
  components: {},
  props:['shuffledText'],
  methods:{
    onSubmit(e) {
      e.preventDefault();
      this.$emit('shuffle-text',this.text);
    },
  },
  data() {
    return {
      text:'',
    }
  }
};
</script>
