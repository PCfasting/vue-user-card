<template>
  <div class="user-card">
        <img class="user-photo" v-bind:src="value.link_ing">
        <p class="user-nickname">{{value.nickname}}</p>
        <p class="user-name">
            {{value.nickname}}
            <br>
            {{value.name}}
        </p>
        <hr>
        <p class="user-info-item">
            <img src="../assets/location.png">
            {{value.address}}
        </p>
        <p class="user-info-item">
            <img src="../assets/mail.png">
            {{value.email}}
        </p>
        <p class="user-info-item">
            <img src="../assets/phone.png">
            {{value.number}}
        </p>
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: ['value'],
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.user-card {
    width: 300px;
    padding: 20px;
    border-radius: 10px;
    margin-top: 100px;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    color: #2c3e50;
    box-shadow: 0 0 15px 0 rgba(50, 50, 50, 0.2);
    text-align: center;
}

.user-card .user-photo {
    box-sizing: border-box;
    height: 150px;
    margin-top: -100px;
    border-radius: 50%;
    border: 3px solid #ccc;
}

.user-card .user-name {
    font-size: 30px;
    font-weight: 900;
    line-height: 1.4;
    margin: 5px 0;
}

.user-card .user-nickname {
    color: #a0a9b3;
    font-size: 18px;
    margin: 5px 0;
    font-family: monospace;
}

.user-card hr {
    height: 4px;
    width: 50px;
    margin: 10px auto;
    background-color: #2c3e50;
}

.user-card .user-info-item img {
    vertical-align: middle;
    margin-right: 5px;
}
</style>
