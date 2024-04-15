<template>
    <div class="btnContainer">
        <div class="conjuntoBtn">
            <div class="arribaIzq esquina"></div>
            <div class="centroBtn"></div>
            <div class="arribaDrch esquina"></div>
        </div>
        <button class="btn">
            <div>
                <slot></slot>
            </div>
        </button>
        <div class="conjuntoBtn">
            <div class="abajoIzq esquina"></div>
            <div class="centroBtn"></div>
            <div class="abajoDrch esquina"></div>
        </div>
    </div>
</template>

<style>
.btnContainer {
    height: 80px;
    width: 200px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.btnBorde {
    display: inline-block;
}

.btn {
    background-color: black;
    color: white;
    font-family: Elianto;
    height: 45px;
    width: 170px;
    font-size: 1.2rem;
    border: none;
    padding: 0;
    cursor: pointer;
}

.btn > div{
    padding-bottom: 4px;
}

.conjuntoBtn {
    display: flex;
    justify-content: space-between;
}

.centroBtn {
    width: 170px;
}

.esquina {
    width: 8px;
    height: 8px;
    transition: padding 0.3s ease;
}

.arribaIzq {
    border-top: solid 2px rgba(134, 194, 50, 1);
    border-left: solid 2px rgba(134, 194, 50, 1);
}

.arribaDrch {
    border-top: solid 2px rgba(134, 194, 50, 1);
    border-right: solid 2px rgba(134, 194, 50, 1);
}

.abajoIzq {
    border-bottom: solid 2px rgba(134, 194, 50, 1);
    border-left: solid 2px rgba(134, 194, 50, 1);
}

.abajoDrch {
    border-bottom: solid 2px rgba(134, 194, 50, 1);
    border-right: solid 2px rgba(134, 194, 50, 1);
}

.btnContainer:hover>div>.esquina {
    padding: 3px;
}</style>