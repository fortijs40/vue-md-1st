<script>
  export default {
    data() {
      return {
        isLoggedIn: false,
        user: {
            name: 'Ralfs',
            surname: 'Laipiņš',
            code: 'IT21014',
        },
      };
    },
    computed: {
        full_name() {
        return `${this.user.name} ${this.user.surname}`;
        },
    },
    methods: {
      toggleLoginStatus() {
        if (this.isLoggedIn) {
          if (confirm("Do you want to log out?")) {
            this.isLoggedIn = false;
            this.$emit('toggleLoginStatus');
          }
        } else {
          if (confirm("Do you want to log in?")) {
            this.isLoggedIn = true;
            this.$emit('toggleLoginStatus');
          }
        }
      },
    },
  };
</script>
<template>
    <header :style="{ backgroundColor: isLoggedIn ? 'rgb(107, 0, 207)' : 'rgb(102, 96, 104)' }">
      <div class="values">
        <div class="logoAndName">
          <img src="@/assets/wlogo.svg" alt="Logo" id="logo" />
          <h1>BIG PAPA KRAKEN</h1>
        </div>
        <div class="rightside">
          <div v-show="isLoggedIn" class="user-info">
            <div class="avatar"></div>
            <div id="fullname">{{ full_name }}</div>
          </div>
          <button id="logButton" @click="toggleLoginStatus">{{ isLoggedIn ? 'LOGOUT' : 'LOGIN' }}</button>
        </div>
      </div>
    </header>
  </template>
  <style>
  #logo{
    width: 50px;
    height: 50px;
    margin-right: 20px;
  }
  .logoAndName{
    display: flex;
    align-items: center;
  }
  #fullname {
    font-size: 20px;
    font-weight: 500;
    color:white;
  }
  .user-info{
    display: flex;
    padding-right: 10px;
    height: 30px;
    border-right: 2px solid white;
    align-items: center;
  }
  .rightside {
    display: flex;
    height: 40px;
    align-items: center;
  }
  .values{
    padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  }
  header {
    transition: background-color 0.5s ease;
    width: 100%;
    justify-content: space-between;
  }
  #logButton{
    margin-left : 10px;
    padding: 8px 40px;
    background-color: rgb(21, 2, 37); 
    border: none;
    border-radius: 14px;
    cursor: pointer;
    color: white;
    font-weight: bold;
    font-size: 16px;
  }
  .avatar {
    background-color: rgb(133, 141, 141);
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 10px;
    border: 2px solid white;
  }
  
  
  </style>

  