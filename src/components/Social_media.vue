<template>
    <div class="social-handles">
        <ul>
            <li>
                <a :href="'https://www.instagram.com/'+ socialMedia.instagram" target="_blank" :title="socialMedia.instagram">
                    <i class="fab fa-instagram"></i>
                </a>
            </li>
            <li>
                <a :href="'https://twitter.com/'+ socialMedia.twitter" target="_blank" :title="socialMedia.twitter">
                    <i class="fab fa-twitter-square"></i>
                </a>
            </li>
            <li>
                <a :href="'https://www.snapchat.com/add/'+ socialMedia.snapchat" target="_blank" :title="socialMedia.snapchat">
                    <i class="fab fa-snapchat-square"></i>
                </a>
            </li>
            <li>
                <a :href="'mailto:'+ socialMedia.email" target="_blank" :title="socialMedia.email">
                    <i class="fas fa-envelope-square"></i>
                </a>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    data(){
        return{
            socialMedia:{}
        }
    },
    methods:{
        fetchData(){
            fetch('https://hirng-x2021.glitch.me/api')
            .then(res => res.json())
            .then(data => {
                this.socialMedia = data.social_media
            })
            .catch(err => console.log(err.message))
        }
    },
    mounted(){
        this.fetchData();
    }
}
</script>