<template>
  <div class="nav-bar">
    <div class="nav-items">
      <div class="nav-item active">Home</div>
      <div class="nav-item">Discover</div>
      <div class="nav-item">Register</div>
    </div>
  </div>

  <div class="login-section">
    <div class="login-section-title">
      <p>Please log in to start using</p>
      <h4>Booked Tool</h4>
    </div>

    <div class="login-section-input">
      <input type="text" name="" id="" class="login-input input" placeholder="Email">
      <input type="text" name="" id="" class="pass-input input" placeholder="Password">
      <button class="btn-login">Login</button>
    </div>
  </div>

      <TabsWrapper>
        <TabItem title="Tab 1">Content from Tab 1</TabItem>
        <TabItem title="Tab 2">Content from Tab 2 Lorem ipsum dolor sit amet.</TabItem>
        <TabItem title="Tab 3">Content from Tab 3 Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptates, ipsa.</TabItem>
        <TabItem title="Tab 4">Content from Tab 4 Lorem ipsum dolor sit amet.</TabItem>
    </TabsWrapper>

  <div class="get-in-touch">
    <h4>Get In Touch</h4>
    <p>Want to get in touch? We'd love to hear from you. Here's how you can reach us.</p>

    <input type="text" name="" id="" class="search-input input" placeholder="Search...">

    <div class="feedback">
      <h4>Feedback</h4>
      <input type="text" name="" id="" class="first-input input" placeholder="First">
      <input type="text" name="" id="" class="last-input input" placeholder="Last">
      <input type="text" name="" id="" class="message-input input" placeholder="Message">
      <button class="btn-send">Send</button>
    </div>
  </div>
</template>

<style scoped>
.nav-bar{
  background: rgb(237, 237, 237);
}
.nav-bar .nav-items {
  display: flex;
  flex-direction: row;
  justify-content: end;
}

.nav-items .nav-item {
  margin: 10px 30px;
  border-radius: 35px;
  padding: 10px;
  width: 100px;
  text-align: center;
  color: black;
}

.nav-items .active {
  background: rgb(201, 200, 200);
}

.login-section{
  display: flex;
  justify-content: center;
  background: rgb(201, 200, 200);
}

.login-section .login-section-title{
  margin-right: 20px;
}

.login-section-input .input{
  height: 30px;
  width: 200px;
  margin-right: 15px;
}

.login-section-input{
  padding-top: 30px;
}

.login-section-input button{
  height: 40px;
  width: 100px;
  color: white;
  background: rgb(32, 118, 248);
  border: none;
  border-radius: 5px;
}
</style>

<script setup>
import { useSlots, ref , provide} from 'vue'
import TabsWrapper from './TabsWrapper.vue'
import TabItem from './TabItem.vue'
const slots = useSlots()
const tabTitles = ref(slots.default().map(tab => tab.props.title))
const selectedTitle = ref(tabTitles.value[0])
provide('selectedTitle', selectedTitle)
</script>