<template>
  <footer>
    <span>
        <a href="mailto:cathy.sengmany.pro@gmail.com">
            <FontAwesomeIcon
                        icon={faEnvelopeSquare}
                        size="2x"
                        className="footer-icon"
                    />
        </a>
        <a
                    href="https://github.com/csengmany"
                    target="_blank"
                    rel="noreferrer"
        >
            <FontAwesomeIcon
                        icon={faGithubSquare}
                        size="2x"
                        className="footer-icon"
                    />
        </a>
                <a
                    href="https://www.linkedin.com/in/cathy-sengmany/"
                    target="_blank"
                    rel="noreferrer"
                >
                    <FontAwesomeIcon
                        icon={faLinkedin}
                        size="2x"
                        className="footer-icon"
                    />
                </a>
            </span>
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