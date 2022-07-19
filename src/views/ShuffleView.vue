<template>
    <Form @shuffle-text="shuffleText" :shuffledText="shuffledText"/>
</template>

<script>
import Form from "../components/Form.vue";
export default {
    name:'ShuffleView',
    components:{
        Form
    },
    methods:{
        async shuffleText(text){
            const res = await fetch(`http://127.0.0.1:5000/api/v1/shuffle/${text}`,{
                method:'POST',
                headers:{
                    'Content-Type':'application/json',
                },
                body:JSON.stringify({})
            });

            if(res.status === 200) {
                const data = await res.json();
                this.shuffledText = data.shuffled_text;
            }else {
                console.log(res);
            }
            
        }
    },
    data(){
        return {
            shuffledText:''
        }
    }
}
</script>