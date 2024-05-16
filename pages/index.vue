<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h2>Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>

            <div class="col-lg-6">
                <nuxt-link to="/buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body">
                            <h2>Cari Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
        </div>
    </div>
    <h2 style="margin : 30px;"><strong>STATISTIK</strong></h2>
    <div class="container-fluid">
        <div class="row justify-content-evenly rounded-5">
            <div class="col-5">
                <div class="raccing">
                    <h2><strong>1</strong>pengunjung</h2>
                </div>
            </div>
            <div class="col-5">
                <div class="raccing1">
                    <h2><strong>3</strong>buku</h2>
                </div>
            </div>
        </div>
    </div>
</template>


<script setup>
</script>



<style scoped>
.card { 
    height:250px;
    box-shadow: 1px 1px 10px #424242;
}
.card.bg-pengunjung {
    background: url('../assets/img/kunjungan.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    margin-bottom: 30px;
}
.card.bg-buku {
    background: url('../assets/img/buku.png') no-repeat center center;
    background-size: cover;
}

.raccing{
    height: 200px;
    box-shadow: 1px 1px 10px;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #E1B4F1;
}

.raccing1{
    height: 200px;
    box-shadow: 1px 1px 10px;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #C1F5E9;
}
</style>