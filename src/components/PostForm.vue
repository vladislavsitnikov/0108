<template>
    <section class="post">
        <div v-for="item in posts" >
            <div class="post-name">
                <h2>{{item.name}}</h2>
                <p>
                    {{item.data}}
                </p>
            </div>
            <div class="post-txt">
                {{ item.text }}
            </div>
        </div>
        <form @submit.prevent>
            <input 
                @input="text = $event.target.value"
                :value="text" 
                type="text" 
            >
            <button @click="createPost">Send a message</button>
        </form>
    </section>
</template>

<script>

export default {
  name: 'PostForm',
  data(){
    return {
        posts   : [
            {
                id: 1,
                name: "Samuel Jackson", 
                text: 'Hey Eva! Youre cool. Nice pic!',
                data: '13 Apr 2022'
            },
            {
                id: 2,
                name: "Angela Deimon", 
                text: 'Thanks for your services! We really liked the ocean view room. We hope to cooperate in the near future. We are sure you will do everything to make our next holiday fantastic.',
                data: '10 Apr 2022'
            },
            {
                id: 3,
                name: "Ronald Harris", 
                text: 'Eva, hello! There is such a question: How can I contact you if I am abroad in roaming?',
                data: '8 Apr 2022'
            },
        ], 
        text: '',
    }
  },
  methods:{
    createPost(){
        const newPost = {
            id: Date.now(),
            text: this.text, 
        }
        this.posts.push(newPost);
        this.text ='';
    }
  }
}
</script>
<style lang="scss" scoped>
.post{
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.post-name{
    display: flex;
    align-items: baseline;
}
.post-name h2{
    font-weight: 700;
    font-size: 14px;
    line-height: 19px;
    color: #333333;
    padding-right: 10px;
}
.post-name p{
    font-weight: 400;
    font-size: 11px;
    line-height: 19px;
    color: #808080;
}
.post-txt{
    border:10px solid #fff;
    padding: 20px;
    background-color: #f2fbff;
    border-image: url("@/assets/Rectangle\ 6.png") 18;
    border-right-width: 3px;
    border-left-width: 5px;
    border-bottom-width: 3px;
    border-top-width: 11px;
    margin-bottom: 10px;
}
form{
    display: flex;
    justify-content: center;
    background: #F2F2F2;
    width: 550px;
    margin: 0 auto;
    padding: 20px;
    flex-direction: column;
    align-items: center;
    margin-top: 20px;
}
input{
    width: 447px;
    height: 63px;
    background: #FFFFFF;
    border: 1px solid #000000;
    border-radius: 1px;
}
button{
    width: 281px;
    height: 43px;
    background: #FDD639;
    border-radius: 23px;
    font-weight: 700;
    font-size: 16px;
    line-height: 21px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 20px;
    text-align: center;
    color: #333333;
    cursor: pointer;
    border: none; 
    outline: none; 
}
@media (max-width: 600px){
    .post-txt{
        width: 370px;
    }   
    .post{
        align-items: center;
    }
    form{
        width: -webkit-fill-available;
    }
}
@media (max-width: 490px){
    input{
        width: 350px;
    }
}
@media (max-width: 425px){
    .post-txt{
        width: 290px;
    }  
    form{
        padding: 20px 0;
    }
}

</style>