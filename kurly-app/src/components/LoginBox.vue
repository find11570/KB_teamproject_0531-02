<template>
    <div>
        <h1>로그인</h1>
        <hr class="line">
        <form @submit.prevent="submitForm">
            <label for="id">아이디*:</label>
            <input type="text" id="id" name="id" v-model="user.id" required>
            <div class="error" id="id-error"></div>

            <label for="password">비밀번호*:</label>
            <input type="password" id="password" name="password" v-model="user.password" required>
            <div class="error"></div>

            <button type="submit">로그인</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            user: { id: '', password: '' }
        };
    },
    methods: {
        submitForm() {
            alert('안녕하세요 ' + this.user.id + '님');
        }
    }
};
</script>

<style scoped>
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
