<template>
    <div>
        <h1>회원가입</h1>
        <hr class="line">
        <form action="" method="post" @submit="validateForm">
            <label for="id">아이디*:</label>
            <input type="text" id="id" name="id" v-model="user.id" required>
            <button type="button" @click="checkId">중복확인</button>
            <div id="id-error" class="error"></div>

            <label for="password">비밀번호*:</label>
            <input type="password" id="password" name="password" required>
            <div class="error"></div>

            <label for="confirmPassword">비밀번호 확인*:</label>
            <input type="password" id="confirmPassword" name="confirmPassword" required>
            <div class="error"></div>

            <label for="name">이름*:</label>
            <input type="text" id="name" name="name" required>
            <div class="error"></div>

            <label for="email">이메일*:</label>
            <input type="email" id="email" name="email" required>
            <button type="button" @click="checkEmail">중복확인</button>
            <div id="email-error" class="error"></div>

            <label for="phone">휴대폰*:</label>
            <input type="tel" id="phone" name="phone" required>
            <button type="button" @click="sendVerificationCode">인증번호 받기</button>
            <input type="text" id="verificationCode" name="verificationCode" placeholder="인증번호 입력">
            <div class="error"></div>

            <label for="address">주소*:</label>
            <input type="text" id="address" name="address" required>
            <button type="button" @click="searchAddress">주소 검색</button>
            <div class="error"></div>

            <label for="gender">성별*:</label>
            <select id="gender" name="gender" required>
                <option value="">선택</option>
                <option value="male">남자</option>
                <option value="female">여자</option>
            </select>

            <label for="birthday">생년월일:</label>
            <input type="date" id="birthday" name="birthday">
            <div class="error"></div>

            <label for="referrerId">친구 초대 (선택):</label>
            <input type="text" id="referrerId" name="referrerId">
            <div class="error"></div>

            <label for="agreeTerms">이용약관 동의*:</label>
            <input type="checkbox" id="agreeTerms" name="agreeTerms" required>
            <a href="#" @click="showTerms">약관보기</a>
            <div class="error"></div>

            <label for="agreePrivacy">개인정보 수집∙이용 동의*:</label>
            <input type="checkbox" id="agreePrivacy" name="agreePrivacy" required>
            <a href="#" @click="showPrivacy">약관보기</a>
            <div class="error"></div>

            <label for="agreeMarketing">무료배송, 할인쿠폰 등 혜택/정보 수신 동의(선택):</label>
            <input type="checkbox" id="agreeMarketing" name="agreeMarketing">
            <div class="error"></div>

            <button type="submit" @click="submitForm">회원가입</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            user: { id: '', pwd: '' }
        }
    },
    methods: {
        submitForm() {
            alert('안녕하세요 ' + this.user.id + '님');
        }
    }

    
}
</script>



<style>
h1 {
    text-align: center;
    margin-bottom: 20px;
}

label {
    display: block;
    margin-bottom: 5px;
}

input[type="text"],
input[type="password"],
input[type="tel"],
select {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    box-sizing: border-box;
}

button {
    background-color: white;
    color: #8B00FF;
    padding: 10px 20px;
    border: 1px solid #8B00FF;
    cursor: pointer;

}

.error {
    color: red;
    margin-top: 5px;
}
</style>