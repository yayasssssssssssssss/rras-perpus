<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">PILIHLAH BUKU YANG INGIN ANDA BACA</h2>
                <div class="my-3">
                    <form @Submit.prevent="getBooks">
                    <input v-model="keyword" type="search" class="form-contol rounded-5" placeholder="mau baca apa hari ini ?">
                    </form>
                </div>
                <div class="my-3 text-muted">menampilkan 3 dari 3</div>
                <div class="row">
                    <div v-for="(book,i) in books" :key="i" class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <nuxt-link to="rincian-buku/">
                                <img :src="book.cover" class="cover" alt=" cerita">
                                </nuxt-link>
                            </div>
                        </div>
                    </div>
                    <div v-for="(book,i) in books" :key="i" class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <nuxt-link to="http://localhost:3000/rincian-buku/buku2">
                                <img :src="book.cover" class="cover" alt="cinta">   
                                </nuxt-link>
                            </div>
                        </div>
                    </div>
                    <div v-for="(book,i) in books" :key="i" class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <nuxt-link to="http://localhost:3000/rincian-buku/buku3">
                                <img :src="book.cover" class="cover" alt="malin">
                                </nuxt-link>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <nuxt-link to="http://localhost:3000/">
                    <button type="submit" class="btn btn-dark btn-lg rounded-5 px-5">kembali</button>
                </nuxt-link>
    </div>
</template>

<script setup>
const supabase = useSupabaseClient()
const books = ref([])
const getbooks = async () => {
    const { data, error } = await supabase.from('buku').select(`*, kategori(*)`)
    if(data) books.value = data
}

onMounted(() => {
    getbooks()
})

const keyword = ref('')

const getBooks= async () => {
    const { data, error } = await supabase.from('buku').select(`*,kategori(*)`)
    .ilike('judul', `%${keyword.value}%`)
    if(data) books.value = data
}

</script>