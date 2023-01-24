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
        <input @click="addDocument" type="button" class="inp" value="Submit">
    </div>
</div>

</template>

<script>


export default{

    name: "my-form",
    data(){
        return{
            uname : "",
            uemail : "",
            unum : "",
            umsg : "",
            db : null
        }
    },
}

</script>

<style>

</style>