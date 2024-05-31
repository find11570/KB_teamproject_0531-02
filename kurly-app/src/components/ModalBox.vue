<template lang="">
    <div class="modal-box">
        <div class="div-row">
            <div class="name-div">
                제목
            </div>
            <div class="value-div">
                [{{this.modalData.type}}] {{this.modalData.title}}
            </div>
        </div>
        <div class="div-row">
            <div class="name-div">
                작성자
            </div>
            <div class="value-div">
                {{this.modalData.writer}}
            </div>
        </div>
        <div class="div-row">
            <div class="name-div">
                작성일
            </div>
            <div class="value-div">
                {{this.modalData.createdAt}}
            </div>
        </div>
        <div class='content-box'>
            {{this.modalData.content}}
        </div>
    </div>
</template>
<script>
export default {
    props : ['modalData']
}
</script>
<style setup>
    .modal-box {
        border : 1px solid black;
        width : 700px;
    }
    .div-row {
        display : flex;
    }

    .name-div {
        width:150px;
        padding :10px;
        font-weight: bold;
        background-color: rgb(240, 240, 240);
        text-align: center;
    }
    .value-div {
        padding: 10px 30px;
        font-weight: bold;
    }
    .content-box {
        padding : 70px;
    }
</style>