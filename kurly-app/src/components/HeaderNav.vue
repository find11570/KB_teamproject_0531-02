<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<template lang="">
    <header>
    <div class="nav-box">
        <div clas="img-box">
          <a id="img-a" href="/"><img src="@/assets/kurly.png"/></a>
        </div>
      <nav>
        <RouterLink to="/member">회원가입</RouterLink>
        <RouterLink to="/login" id="center">로그인</RouterLink>
        <RouterLink to="/board">고객센터</RouterLink>
      </nav>
    </div>
  </header>
</template>
<script>
export default {
    
}
</script>
<style scoped>
    .nav-box {
      display : flex;
    }
    nav {
      margin-left : 40px;
      margin-top : 10px;
    }
    img {
      width: 100px;
      height : 50px;
    }
    a {
      color : gray;
      padding : 5px 20px;
    }
    a:focus {
      color : purple;
      font-weight : bold;
    }
    
    a:hover {
      background-color: white;

    }

    #center {
      border-left : 1px solid gray;
      border-right: 1px solid gray;
    }

</style>