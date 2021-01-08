<template>
    <div class="main-content">
        <div>
            <h1>{{name}}</h1>
            <img :src="bigImg" class="big-img" alt="aquila aveion">
            <nav class="nav">
                <ul>
                    <li><a href="#">Home</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#"><img :src="profileImg" class="profile-img"  alt="Profile Image"></a></li>
                    <li><a href="#">Gallery</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>
        </div>
    </div>
    <comp-social-media/>
</template>


<script>
import compSocialMedia from './Social_media.vue';
import aveionImg from '../assets/images/aveion.png';
import profilePhoto from '../assets/images/profile.jpg';


export default {
    data(){
        return{
            name: '',
            bigImg: aveionImg,
            profileImg: profilePhoto
        }
    },
    methods:{
        fetchData(){
            fetch('https://hirng-x2021.glitch.me/api')
            .then(res => res.json())
            .then(data => {
                this.name = data.name;
            })
            .catch(err => console.log(err.message))
        }
    },
    components:{
        compSocialMedia
    },
    mounted(){
        this.fetchData();
    }
}
</script>