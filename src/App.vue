<template>
  <main>
    <div class="header-wrap">
      <img src="@/assets/unsplash_O3ymvT7Wf9U.jpg" alt="logo">
      <div class="header-text">
        <h2>Eva Jonson</h2>
        <span>Sales Manager</span>
        <div class="header-blog">
          <p>I will find the best offers for you. My services are absolutely free.</p>
        </div>
      </div>
    </div>
    <div class="service">
      <div class="service-logo">
        Services
      </div>
      <ProgressBar/>
    </div>
    <div class="reviews">
      <div class="reviews-text">
        <h2>Latest reviews</h2>
        <a href="#">All reviews</a>
      </div>
      <div class="reviews-lick">
        <div v-on:click="addLike">{{likes}}</div>
        <div>14</div>
      </div>
    </div>
    <PostForm/>
</main>
  
</template>

<script>
import ProgressBar from "@/components/ProgressBar.vue";
import PostForm from "@/components/PostForm.vue";
export default {
  name: "AppPage",
  components: {
    ProgressBar,
    PostForm,
  },
  data(){
    return{
      likes: 131,
    }
  },
  methods:{
    addLike(){
      this.likes += 1;
    },
  }
};
</script>

<style>
*{
  padding: 0;
  margin: 0;
}
main{
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  max-width: 550px;
  margin: 0 auto;
  font-family: 'Arial';
  font-style: normal;
}
.header-wrap{
  display: flex;
}
.header-wrap img{
  width: 176px;
  height: 169px;
  border-radius: 50%;
  z-index: 100;
}
.header-text{
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.header-text h2{
  font-weight: 700;
  font-size: 16px;
  line-height: 20px;
  color: #333333;
}
.header-text span{
  font-weight: 400;
  font-size: 12px;
  line-height: 20px;
  color: #808080;
}
.header-blog{
  display: flex;
  align-items: center;
  justify-content: center;
  width: 364px;
  height: 54px;
  background: #FFFBC8;
  border: 1px solid #DADADA;
  border-radius: 5px;
  margin-left: -53px;
  z-index: 0;
}
.header-blog p{
  max-width: 200px;
  font-weight: 400;
  font-size: 14px;
  line-height: 20px;
  color: #333333;
}
.service-logo{
  display: flex;
  justify-content: flex-end;
  font-weight: 400;
  font-size: 13px;
  line-height: 15px;
  color: #333333;
}
.reviews{
  display: flex;
  justify-content: space-between;
  width: 100%;
}
.reviews-text{
  display: flex;
  align-items: center;
}
.reviews-text h2{
  color: #333333;
  font-weight: 700;
  font-size: 16px;
  line-height: 16px;
  padding-right: 10px;
}
.reviews-lick{
  display: flex;
  padding: 20px 0;
}
.reviews-lick div{
  position: relative;
  padding-right: 20px
}
.reviews-lick div:nth-child(1)::after{
  content: '';
  position: absolute;
  background-image: url('@/assets/like.png');
  background-repeat: no-repeat;
  width: 16px;
  height: 14px;
  left: -16px;
  top: 4px;
}
.reviews-lick div:nth-child(2)::after{    
  content: '';
  position: absolute;
  background-image: url('@/assets/comment.png');
  background-repeat: no-repeat;
  width: 16px;
  height: 14px;
  left: -16px;
  top: 4px;
}
@media (max-width: 500px){
  .header-blog {
      width: 258px;
      justify-content: end;
  }
  .header-wrap img {
      width: 133px;
      height: 133px;
  }
}
</style>
