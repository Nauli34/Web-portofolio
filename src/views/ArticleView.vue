<template>
    <div class="w-full md:w-3/5 h-20 mx-auto md:mt-5">
        <div class="bg-white rounded-xl mx-3 p-5 md:p-10 md:mx-0">
            <div>
                <h1 class="text-xl md:text-4xl text-black text-left font-bold leading-relaxed">{{ title }}</h1>
                <div class="mt-3 text-left text-gray-800 text-sm">Published at <span>{{ date }}</span></div>
                <div class="h-[2px] w-20 my-5 md:my-10 bg-[#ffdb70] md:w-1/3 aos-init aos-animate mr-2"></div>
                <div>
                    <div class="relative w-full" style="padding-top: 50%;">
                        <img :src="image" class="absolute top-0 left-0 rounded-lg w-full h-full object-cover" alt="Thumbnail">
                    </div>
                </div>
                <div class="text-left text-black mt-8" v-html="content"></div>
            </div>
        </div>
    </div>
</template>

<script>
import { useRoute } from 'vue-router';

export default {
    data() {
        return {
            route: useRoute(),
            title: 'Gempa Bumi Berkekuatan 6.5 SR Guncang Maluku Utara',
            image: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/Gempa_Bumi_di_Maluku_Utara_%282021%29.jpg/640px-Gempa_Bumi_di_Maluku_Utara_%282021%29.jpg',
            date: '2024-09-25',
            content: `<p>Hari ini, warga Maluku Utara dikejutkan oleh gempa bumi berkekuatan 6.5 skala Richter yang terjadi pada pukul 14:30 WIB. Pusat gempa terletak di kedalaman 10 km, sekitar 50 km dari kota Ternate.</p> 
                      <p>Menurut Badan Meteorologi, Klimatologi, dan Geofisika (BMKG), hingga saat ini belum ada laporan tentang kerusakan serius. Namun, warga diimbau untuk tetap waspada dan mengikuti arahan dari pihak berwenang.</p> 
                      <p>Gempa ini dirasakan cukup kuat di beberapa daerah, dengan banyak warga yang berlari keluar rumah untuk menghindari kemungkinan setelah gempa.</p> 
                      <p>Petugas sedang melakukan peninjauan untuk memastikan kondisi di lapangan dan akan memberikan informasi lebih lanjut kepada publik.</p>`,
        }
    },
    mounted() {
        this.getDetails();
    },
    methods: {
        async getDetails() {
            // The following lines can be uncommented if you're using an API to fetch details based on an id
            /*
            const id = this.route.params.id; 
            axios.get('https://api.example.com/news/' + id)
                .then(response => {
                    this.title = response.data.title;
                    this.image = response.data.image;
                    this.date = response.data.date;
                    this.content = response.data.content;
                })
                .catch(error => {
                    console.error("There was an error fetching the news data:", error);
                });
            */
        }
    }
}
</script>

<style scoped>
body {
    background: url('https://images.unsplash.com/photo-1506748686214-e9df14d4d9d0?fit=crop&w=1920&q=80') no-repeat center center fixed;
    background-size: cover;
}
</style>
