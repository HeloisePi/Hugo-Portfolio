<script>
    export let title;
    export let title2;
    export let scroll;
</script>

<section id="{title}">

    <h1>
        {title}
    </h1>


    {#if title2}
    <h2>
        {title2}
    </h2>
    {/if}

    <a href="{scroll}" class="scroll">
        <img class="textScroll" src="/scroll.svg" alt="Défilez en bas">
        <img class="arrow" src="/arrow.svg" alt="Défilez en bas"/>
    </a>
</section>
<style>
    section{
        /* position: absolute; */
        /* top: 0; */
        padding-top: 20vh;
        /* height: 190vh; */
        height: 100vh; 
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        gap: 1rem;
        position: relative;
        width: 100%;
        overflow: hidden;
    }

    @media screen and (max-height: 1000px) {
                section h1{
                    font-size: 48px;
                }
                h2{
                    font-size: 28px;
                }
                #hero .scroll{
                    width: 70px;
                    margin-top: 0px;
                    
                }
                #hero .arrow{
                    width: 15px;
                    height: auto;
                }

            }
            @media screen and (max-height: 500px) {
                #hero{
                    gap: 0;
                }
                h2{
                    margin-bottom: 40px;
                }
            }


    .scroll{
        margin-top: 5vh;
        position: relative;
        width: 116px;
        height: 114px;
    }

    .scroll img{
        position: absolute;

    }

    .textScroll{
        animation: Rotate linear infinite  20s;
    }

    .arrow{

        left: 50%;
        transform: translate(-50%, 100%);
        animation: upDown linear infinite  5s;
    }


    @keyframes upDown{
        0%{
            transform: translate(-50%, 100%);
        }

        50%{
            transform: translate(-50%, 80%);
        }

        100%{
            transform: translate(-50%, 100%);
        }
    }

    @keyframes Rotate{
        0%{
            transform: rotate(0deg);
        }
        100%{
            transform: rotate(-360deg);
        }
    }
</style>