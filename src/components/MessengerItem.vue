<template>
    <li>
        <div class="d-flex">
            <h3>{{msn.name}}</h3>
            <p class="ml-2">{{msn.data}}</p>
        </div>
        <div class="mesg">{{msn.msg}}</div>
    </li>
</template>

<script>
    export default {
        props: {
            msn:{
                type: Object,
                required: true
            }
        },
        name: "MessengerItem"
    }
</script>

<style>
h2 {
    font-size: 14px;

}
    p {
        font-size: 11px;
    }
.mesg {
    position: relative;
    padding: 15px 20px;
    background-color: #f2fbff;
    border: 1px solid #cfcfcf;
    border-radius: 2px;
}
 .mesg:after {
     content: '';
     position: absolute;
    top: -12px;
    left: 21px;
     border: 8px solid transparent;
     border-bottom: 8px solid #f2fbff;
     border-left: 8px solid #f2fbff;
 }.mesg:before {
     content: '';
     position: absolute;
       top: -15px;
       left: 20px;
     border: 8px solid transparent;
     border-bottom: 8px solid #cfcfcf;
       border-left: 8px solid #cfcfcf;
 }
</style>
