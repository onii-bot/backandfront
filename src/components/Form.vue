<template>
<div class="wrap">
    <div class="main">
        <h1 class="head">
            contact us
        </h1>
        <input type="text" class="inp" name="name" placeholder="Name" v-model="uname">
        <input type="email" class="inp" name="email" placeholder="Email" v-model="uemail">
        <input type="tel" class="inp" name="contact" placeholder="Contact No." v-model="unum">
        <textarea  v-model="umsg" name="description" id="description" cols="30" rows="10" class="inp" placeholder="Type your message here"></textarea>
        <input @click="sendpost" type="button" class="inp" value="Submit">
    </div>
</div>

</template>

<script>
import axios from 'axios'

export default{

    name: "my-form",
    data(){
        return{
            uname : "",
            uemail : "",
            unum : "",
            umsg : ""
        }
    },

    methods: {
        async sendpost(){
            if(this.uname == "" || this.uemail == "" || this.unum == ""){
                return
            }
            let post = {
                name : this.uname,
                email : this.uemail,
                num : this.unum,
                msg : this.umsg,
            }
            let result = await axios.post("http://localhost:3000/user", post)
            location.reload()
            console.log(result)
        }
    }
}

</script>

<style>

</style>