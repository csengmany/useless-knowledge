<template>
  <footer>
            <span>
                © {{date}}&nbsp;Cathy Sengmany, built with <Logo class="footer-logo"/>
            </span>
  </footer>
</template>

<script>
export default {
    data(){
        return{date:new Date().getFullYear()}
    }

}
</script>

<style>

footer{
    display: flex;
    justify-content: center;
    align-items: center;
}

.footer-logo{
    height: 20px;
    width: 25px;

}
.footer-logo:hover{
    transition-duration:0.5s;
    transform: translateX(20px);
    transform: scale(1.2);
}



</style>