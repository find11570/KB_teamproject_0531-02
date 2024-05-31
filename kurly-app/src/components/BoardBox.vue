<script setup>
import ModalBox from "./ModalBox.vue"
import { ref, reactive } from 'vue';
const popState = ref(false);
    const modalData = ref({});
    const posts = reactive([
        { id : 1, postId : 1, type:'안내', title :'앱푸시 알림센터 서비스 오픈 (2024.02.14)', writer:'컬리', isNotice: true, createdAt :'2024.02.14', content:'글 1 내용입니다.'},
        { id : 2, postId : 2, type:'안내', title :'컬리 소비자 분쟁해결 기준 안내', writer:'컬리', isNotice: true, createdAt :'2024.02.14', content:'글 2 내용입니다.'},
        { id : 3, postId : 674, type:'이벤트', title :'4/17 레고랜드 라이브 이벤트 당첨자 안내', writer:'컬리', isNotice: false, createdAt :'2024.02.14', content:'글 3 내용입니다.'},
        { id : 4, postId : 675, type:'이벤트', title :'4/18 조 말론 런던 라이브 당첨자 안내', writer:'컬리', isNotice: false, createdAt :'2024.02.14', content:'글 4 내용입니다.'},
        { id : 5, postId : 676, type:'안내', title :'컬리멤버스 이용약관 개정 사전 안내', writer:'컬리', isNotice: false, createdAt :'2024.02.14', content:'글 5 내용입니다.'}
    ]);

    const changePopState = (post) => {
        popState.value = !popState.value;
        if (popState.value) {
            modalData.value = post;
        }
    }
</script>
<template>
    <div>
        <div>
            <div class="title-box">
                <div id="t1">공지사항</div>
                <div id="t2">컬리의 새로운 소식들과 유용한 정보들을 한 곳에서 확인하세요.</div>
            </div>
            <div class="table-box mt-5">
                <table class="table">
                    <thead>
                        <tr>
                            <th scope="col">번호</th>
                            <th scope="col">제목</th>
                            <th scope="col">작성자</th>
                            <th scope="col">작성일</th>
                        </tr>
                    </thead>

                    <tbody>
                        <tr v-for="post in posts" :key="post.id" @click="changePopState(post)">
                            <th scope="row">{{(post.isNotice) ? "공지" : post.postId }}</th>
                            <td>[{{post.type}}] {{post.title}}</td>
                            <td>{{post.writer}}</td>
                            <td>{{post.createdAt}}</td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <ModalBox v-if="popState" @close="changePopState()" v-bind:modalData="modalData"></ModalBox>
        </div>
    </div>
</template>
<style scoped>
    .title-box {
        display:flex;
        align-items: center;
    }

    #t1 {
        font-size: 24px;
        font-weight: bold;
    }
    #t2 {
        color : gray;
        font-size: 14px;
        font-weight: bold;
        margin-left : 10px;
    }

</style>