<script>
    let arr = ["./img/cara1.png",
               "./img/cara2.png",
               "./img/cara3.png",
               "./img/cara4.png",
               "./img/cara5.png",
               "./img/cara6.png"]
    let x = 5, y = 5;
    let dado1 = arr[x];
    let dado2 = arr[y];
    let msgBtn = "Tirar los dados";

    function randomNumber() {
        x = Math.floor(Math.random() * 6);
        y = Math.floor(Math.random() * 6);
        let z = Math.floor(Math.random() * 5) + 5;

        function runAnimation() {
            animation();
            z--;
            if (z > 0) {
                setTimeout(runAnimation, 300);
                msgBtn = "Espere...";
            }
            else{
                msgBtn = "Tirar los dados";
            }
        }
        runAnimation();
        dado1 = arr[x];
        dado2 = arr[y];
    }

    function animation() {
        let a = Math.floor(Math.random() * 6);
        let b = Math.floor(Math.random() * 6);
        dado1 = arr[a];
        dado2 = arr[b];
    }
</script>


<main>
    <div class="title">
        <h1>Dados Magicos</h1>
    </div>
    <div class="dados">
        <button class="tirarDados" on:click={randomNumber}>{msgBtn}</button>
         <br>
         <br>
         <img src={dado1} alt="Dado 1">
         <img src={dado2} alt="Dado 2">
    </div>
</main>


<style>
    .title{
        text-align: center;
        color: white;
    }
    .tirarDados {
    display: inline-block;
    padding: 10px 20px;
    background-color: rgb(111, 190, 215);
    color: #fff;
    border: none;
    border-radius: 5px; 
    cursor: pointer;
    font-size: 16px;
    text-align: center;
    text-decoration: none;
    transition: background-color 0.3s ease;
    }

    /* Estilo del botón al pasar por encima */
    .tirarDados:hover {
        background-color: #2980b9; 
    }

    /* Estilo del botón al hacer clic */
    .tirarDados:active {
        background-color: #20729c; 
    }
    .dados{
        text-align: center;
        padding-top: 10px;
    }
    img{
        width: 200px;
        margin: 25px;
        background-color:#8ec1e6;
        border-radius: 10px;
    }
</style>
