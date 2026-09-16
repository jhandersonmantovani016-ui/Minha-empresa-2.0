<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Próximo Nível</title>

<style>

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
    font-family:Arial,Helvetica,sans-serif;
}

body{
    background:#08090d;
    color:#fff;
    min-height:100vh;
}

header{
    padding:25px 20px;
    border-bottom:1px solid #22252d;
    background:#0d0f14;
}

.logo{
    font-size:26px;
    font-weight:800;
}

.logo span{
    color:#7c5cff;
}

.subtitle{
    color:#8d929f;
    margin-top:6px;
    font-size:14px;
}

.container{
    width:100%;
    max-width:950px;
    margin:auto;
    padding:20px;
}

.hero{
    padding:25px;
    border:1px solid #242832;
    border-radius:22px;
    background:linear-gradient(145deg,#151821,#0e1016);
    margin-bottom:20px;
}

.hero h1{
    font-size:28px;
    margin-bottom:8px;
}

.hero p{
    color:#999fac;
    line-height:1.5;
}

.general{
    margin-top:22px;
}

.progress-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:8px;
    color:#a8adb8;
}

.progress-head strong{
    color:#fff;
}

.progress{
    width:100%;
    height:11px;
    background:#252832;
    border-radius:20px;
    overflow:hidden;
}

.progress-fill{
    height:100%;
    width:0%;
    background:#7c5cff;
    border-radius:20px;
    transition:.4s;
}

.stats{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:12px;
    margin-top:20px;
}

.stat{
    padding:18px;
    border-radius:16px;
    background:#101219;
    border:1px solid #252933;
}

.stat span{
    display:block;
    color:#8f95a1;
    font-size:12px;
    margin-bottom:7px;
}

.stat strong{
    font-size:25px;
}

.section-title{
    margin:25px 0 14px;
    font-size:21px;
}

.form{
    background:#11131a;
    border:1px solid #272b35;
    border-radius:20px;
    padding:20px;
}

input,
select{
    width:100%;
    padding:14px;
    margin-bottom:12px;
    background:#090a0f;
    border:1px solid #303541;
    border-radius:12px;
    color:#fff;
    outline:none;
}

input:focus,
select:focus{
    border-color:#7c5cff;
}

button{
    border:0;
    cursor:pointer;
}

.main-btn{
    width:100%;
    padding:14px;
    border-radius:12px;
    background:#7c5cff;
    color:white;
    font-weight:bold;
    font-size:15px;
}

.main-btn:hover{
    opacity:.9;
}

.goal-card{
    background:#11131a;
    border:1px solid #272b35;
    border-radius:20px;
    padding:20px;
    margin-bottom:14px;
}

.goal-type{
    color:#999fac;
    font-size:13px;
    margin-bottom:8px;
}

.goal-card h3{
    font-size:20px;
    margin-bottom:10px;
}

.goal-status{
    display:inline-block;
    padding:6px 10px;
    border-radius:20px;
    font-size:12px;
    margin-bottom:15px;
}

.goal-status.done{
    background:#153521;
    color:#65df91;
}

.goal-status.pending{
    background:#282316;
    color:#e9c45e;
}

.goal-actions{
    display:flex;
    gap:8px;
    margin-top:16px;
}

.small-btn{
    flex:1;
    padding:11px 8px;
    border-radius:10px;
    background:#242832;
    color:#fff;
    font-size:12px;
}

.small-btn.primary{
    background:#7c5cff;
}

.small-btn.danger{
    background:#382027;
    color:#ff8997;
}

.category-card{
    background:#11131a;
    border:1px solid #272b35;
    border-radius:18px;
    padding:18px;
    margin-bottom:12px;
}

.category-title{
    font-weight:bold;
    margin-bottom:12px;
}

.challenge{
    background:#11131a;
    border:1px solid #272b35;
    border-radius:20px;
    padding:20px;
}

.challenge p{
    color:#9298a4;
    margin:8px 0 16px;
}

.days{
    display:grid;
    grid-template-columns:repeat(7,1fr);
    gap:7px;
}

.day{
    min-height:60px;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    border-radius:10px;
    background:#20232b;
    color:#b3b7c1;
    font-size:11px;
    cursor:pointer;
}

.day.done{
    background:#7c5cff;
    color:#fff;
    font-weight:bold;
}

.content-card{
    background:#11131a;
    border:1px solid #272b35;
    border-radius:18px;
    padding:18px;
    margin-bottom:12px;
}

.content-card h3{
    margin-bottom:7px;
}

.content-card p{
    color:#9298a4;
    line-height:1.5;
    font-size:14px;
}

.content-card button{
    margin-top:12px;
    padding:10px 14px;
    border-radius:10px;
    background:#242832;
    color:#fff;
}

.empty{
    text-align:center;
    padding:35px 20px;
    border-radius:18px;
    background:#11131a;
    border:1px solid #272b35;
    color:#8e94a0;
    line-height:1.6;
}

.modal{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.75);
    display:none;
    align-items:center;
    justify-content:center;
    padding:20px;
    z-index:100;
}

.modal.show{
    display:flex;
}

.modal-box{
    width:100%;
    max-width:500px;
    background:#151820;
    border:1px solid #303541;
    border-radius:20px;
    padding:24px;
}

.modal-box h2{
    margin-bottom:12px;
}

.modal-box p{
    color:#b0b5bf;
    line-height:1.6;
    white-space:pre-line;
}

.modal-close{
    width:100%;
    margin-top:20px;
    padding:13px;
    border-radius:12px;
    background:#7c5cff;
    color:#fff;
    font-weight:bold;
}

footer{
    text-align:center;
    padding:30px 20px;
    color:#686e7a;
    font-size:12px;
}

@media(max-width:600px){

    .container{
        padding:15px;
    }

    .hero h1{
        font-size:24px;
    }

    .stats{
        grid-template-columns:1fr 1fr;
    }

    .goal-actions{
        flex-direction:column;
    }

    .days{
        gap:4px;
    }

    .day{
        min-height:55px;
        font-size:9px;
    }
}

</style>
</head>

<body>

<header>

    <div class="container">

        <div class="logo">
            PRÓXIMO <span>NÍVEL</span> 🚀
        </div>

        <div class="subtitle">
            Evolua todos os dias. Construa o seu futuro.
        </div>

    </div>

</header>


<main class="container">


<!-- =========================
     VISÃO GERAL
========================= -->

<section class="hero">

    <h1>Seu próximo nível começa agora.</h1>

    <p>
        Defina seus objetivos, acompanhe seu progresso
        e transforme pequenas ações em grandes resultados.
    </p>


    <div class="general">

        <div class="progress-head">

            <span>Progresso geral</span>

            <strong id="generalPercent">0%</strong>

        </div>

        <div class="progress">

            <div
                id="generalBar"
                class="progress-fill">
            </div>

        </div>

    </div>


    <div class="stats">

        <div class="stat">

            <span>METAS CRIADAS</span>

            <strong id="goalCount">0</strong>

        </div>


        <div class="stat">

            <span>METAS CONCLUÍDAS</span>

            <strong id="completedCount">0</strong>

        </div>

    </div>

</section>



<!-- =========================
     NOVA META
========================= -->

<h2 class="section-title">
    🎯 Criar uma meta
</h2>

<section class="form">

    <input
        id="goalName"
        type="text"
        placeholder="Nome da meta">

    <select id="goalType">

        <option value="financeiro">
            💰 Financeiro
        </option>

        <option value="academia">
            🏋️ Academia
        </option>

        <option value="estudos">
            📚 Estudos
        </option>

        <option value="habitos">
            🧠 Hábitos
        </option>

        <option value="outro">
            🎯 Outro
        </option>

    </select>


    <input
        id="goalTarget"
        type="number"
        min="1"
        placeholder="Meta total">


    <input
        id="goalCurrent"
        type="number"
        min="0"
        placeholder="Quanto já realizou?">


    <button
        class="main-btn"
        onclick="criarMeta()">

        + CRIAR META

    </button>

</section>



<!-- =========================
     METAS
========================= -->

<h2 class="section-title">
    📌 Minhas metas
</h2>

<section id="goalList"></section>



<!-- =========================
     CATEGORIAS
========================= -->

<h2 class="section-title">
    📊 Progresso por categoria
</h2>


<div class="category-card">

    <div class="category-title">
        💰 Financeiro
    </div>

    <div class="progress-head">

        <span>Progresso</span>

        <strong id="financeProgress">
            0%
        </strong>

    </div>

    <div class="progress">

        <div
            id="financeBar"
            class="progress-fill">
        </div>

    </div>

</div>


<div class="category-card">

    <div class="category-title">
        🏋️ Academia
    </div>

    <div class="progress-head">

        <span>Progresso</span>

        <strong id="gymProgress">
            0%
        </strong>

    </div>

    <div class="progress">

        <div
            id="gymBar"
            class="progress-fill">
        </div>

    </div>

</div>


<div class="category-card">

    <div class="category-title">
        📚 Estudos
    </div>

    <div class="progress-head">

        <span>Progresso</span>

        <strong id="studyProgress">
            0%
        </strong>

    </div>

    <div class="progress">

        <div
            id="studyBar"
            class="progress-fill">
        </div>

    </div>

</div>


<div class="category-card">

    <div class="category-title">
        🧠 Hábitos
    </div>

    <div class="progress-head">

        <span>Progresso</span>

        <strong id="habitProgress">
            0%
        </strong>

    </div>

    <div class="progress">

        <div
            id="habitBar"
            class="progress-fill">
        </div>

    </div>

</div>



<!-- =========================
     DESAFIO 7 DIAS
========================= -->

<h2 class="section-title">
    🔥 Desafio de 7 dias
</h2>

<section class="challenge">

    <h3>
        Não quebre a sequência.
    </h3>

    <p>
        Toque em cada dia que você completar.
    </p>

    <div
        id="challengeDays"
        class="days">
    </div>

</section>



<!-- =========================
     CONTEÚDOS
========================= -->

<h2 class="section-title">
    📚 Conteúdos
</h2>


<div class="content-card">

    <h3>
        💰 Mentalidade financeira
    </h3>

    <p>
        Aprenda a controlar seu dinheiro antes
        de tentar aumentar sua renda.
    </p>

    <button onclick="abrirConteudo(
        'Mentalidade financeira',
        'Seu dinheiro precisa ter direção.\\n\\nDefina objetivos, controle seus gastos e crie o hábito de guardar uma parte da sua renda.'
    )">

        Ler conteúdo

    </button>

</div>


<div class="content-card">

    <h3>
        🧠 Evolução diária
    </h3>

    <p>
        Pequenas melhorias feitas todos os dias
        podem mudar completamente sua trajetória.
    </p>

    <button onclick="abrirConteudo(
        'Evolução diária',
        'Não tente mudar tudo de uma vez.\\n\\nEscolha uma pequena ação e repita todos os dias. Consistência transforma esforço em resultado.'
    )">

        Ler conteúdo

    </button>

</div>


<div class="content-card">

    <h3>
        🚀 Próximo nível
    </h3>

    <p>
        Pare de esperar o momento perfeito.
        Comece com o que você tem.
    </p>

    <button onclick="abrirConteudo(
        'Próximo nível',
        'O próximo nível não acontece de um dia para o outro.\\n\\nEle é construído através das decisões que você toma quando ninguém está olhando.'
    )">

        Ler conteúdo

    </button>

</div>


</main>


<footer>

    PRÓXIMO NÍVEL © 2026

</footer>



<!-- =========================
     MODAL
========================= -->

<div
    id="modal"
    class="modal">

    <div class="modal-box">

        <h2 id="modalTitle"></h2>

        <p id="modalText"></p>

        <button
            class="modal-close"
            onclick="fecharConteudo()">

            Fechar

        </button>

    </div>

</div>



<script>


/* =========================
   DADOS
========================= */

let metas =
    JSON.parse(
        localStorage.getItem("pn_metas")
    ) || [];


let desafio =
    JSON.parse(
        localStorage.getItem("pn_desafio")
    ) || [
        false,
        false,
        false,
        false,
        false,
        false,
        false
    ];



/* =========================
   SALVAR METAS
========================= */

function salvarMetas(){

    localStorage.setItem(
        "pn_metas",
        JSON.stringify(metas)
    );

}



/* =========================
   CRIAR META
========================= */

function criarMeta(){

    const nome =
        document.getElementById(
            "goalName"
        ).value.trim();


    const tipo =
        document.getElementById(
            "goalType"
        ).value;


    const alvo =
        Number(
            document.getElementById(
                "goalTarget"
            ).value
        );


    const atual =
        Number(
            document.getElementById(
                "goalCurrent"
            ).value
        ) || 0;


    if(!nome){

        alert("Digite o nome da meta.");

        return;
    }


    if(
        !Number.isFinite(alvo) ||
        alvo <= 0
    ){

        alert("Digite uma meta válida.");

        return;
    }


    if(
        !Number.isFinite(atual) ||
        atual < 0 ||
        atual > alvo
    ){

        alert("O progresso precisa estar entre 0 e a meta total.");

        return;
    }


    metas.push({

        id:Date.now(),

        nome:nome,

        tipo:tipo,

        alvo:alvo,

        atual:atual

    });


    salvarMetas();

    limparFormulario();

    renderizarMetas();

}



/* =========================
   RENDERIZAR METAS
========================= */

function renderizarMetas(){

    const lista =
        document.getElementById(
            "goalList"
        );


    lista.innerHTML = "";


    if(metas.length === 0){

        lista.innerHTML = `
            <div class="empty">
                🎯 Você ainda não criou nenhuma meta.<br>
                Comece com uma pequena meta.
            </div>
        `;


        atualizarProgresso();

        return;
    }


    metas.forEach(meta => {


        let percentual =
            Math.round(
                (meta.atual / meta.alvo) * 100
            );


        percentual =
            Math.max(
                0,
                Math.min(
                    100,
                    percentual
                )
            );


        let concluida =
            percentual >= 100;


        let tipoNome = {

            financeiro:"💰 Financeiro",

            academia:"🏋️ Academia",

            estudos:"📚 Estudos",

            habitos:"🧠 Hábitos",

            outro:"🎯 Outro"

        };


        let status =
            concluida

            ? `<span class="goal-status done">
                ✓ Meta concluída
              </span>`

            : `<span class="goal-status pending">
                ⏳ Em andamento
              </span>`;


        const card =
            document.createElement(
                "div"
            );


        card.className =
            "goal-card";


        card.innerHTML = `

            <div class="goal-type">
                ${tipoNome[meta.tipo] || "🎯 Outro"}
            </div>

            <h3>
                ${escaparHTML(meta.nome)}
            </h3>

            ${status}

            <div class="progress-head">

                <span>
                    ${formatarNumero(meta.atual)}
                    /
                    ${formatarNumero(meta.alvo)}
                </span>

                <strong>
                    ${percentual}%
                </strong>

            </div>

            <div class="progress">

                <div
                    class="progress-fill"
                    style="width:${percentual}%">
                </div>

            </div>

            <div class="goal-actions">

                <button
                    class="small-btn primary"
                    onclick="aumentarMeta(${meta.id})">

                    + Progresso

                </button>

                <button
                    class="small-btn"
                    onclick="editarMeta(${meta.id})">

                    ✏️ Editar

                </button>

                <button
                    class="small-btn danger"
                    onclick="excluirMeta(${meta.id})">

                    🗑️ Excluir

                </button>

            </div>
        `;


        lista.appendChild(card);

    });


    atualizarProgresso();

}



/* =========================
   AUMENTAR PROGRESSO
========================= */

function aumentarMeta(id){

    const meta =
        metas.find(
            item => item.id === id
        );


    if(!meta) return;


    const valor =
        prompt(
            `Quanto você quer adicionar à meta "${meta.nome}"?`
        );


    if(valor === null) return;


    const numero =
        Number(valor);


    if(
        !Number.isFinite(numero) ||
        numero <= 0
    ){

        alert("Digite um número válido.");

        return;
    }


    meta.atual += numero;


    if(meta.atual > meta.alvo){

        meta.atual =
            meta.alvo;

    }


    salvarMetas();

    renderizarMetas();

}



/* =========================
   EDITAR META
========================= */

function editarMeta(id){

    const meta =
        metas.find(
            item => item.id === id
        );


    if(!meta) return;


    const novoNome =
        prompt(
            "Nome da meta:",
            meta.nome
        );


    if(novoNome === null)
        return;


    const novoAlvo =
        prompt(
            "Meta total:",
            meta.alvo
        );


    if(novoAlvo === null)
        return;


    const novoAtual =
        prompt(
            "Quanto já foi realizado?",
            meta.atual
        );


    if(novoAtual === null)
        return;


    const alvo =
        Number(novoAlvo);


    const atual =
        Number(novoAtual);


    if(
        !novoNome.trim() ||
        !Number.isFinite(alvo) ||
        alvo <= 0 ||
        !Number.isFinite(atual) ||
        atual < 0 ||
        atual > alvo
    ){

        alert(
            "Confira os valores informados."
        );

        return;
    }


    meta.nome =
        novoNome.trim();


    meta.alvo =
        alvo;


    meta.atual =
        atual;


    salvarMetas();

    renderizarMetas();

}



/* =========================
   EXCLUIR META
========================= */

function excluirMeta(id){

    const meta =
        metas.find(
            item => item.id === id
        );


    if(!meta) return;


    const confirmar =
        confirm(
            `Excluir a meta "${meta.nome}"?`
        );


    if(!confirmar)
        return;


    metas =
        metas.filter(
            item => item.id !== id
        );


    salvarMetas();

    renderizarMetas();

}



/* =========================
   PROGRESSO GERAL
========================= */

function atualizarProgresso(){

    const completed =
        metas.filter(
            meta =>
                meta.atual >= meta.alvo
        ).length;


    document.getElementById(
        "completedCount"
    ).textContent =
        completed;


    document.getElementById(
        "goalCount"
    ).textContent =
        metas.length;


    if(metas.length === 0){

        definirBarra(
            "general",
            0
        );

        definirBarra(
            "finance",
            0
        );

        definirBarra(
            "gym",
            0
        );

        definirBarra(
            "study",
            0
        );

        definirBarra(
            "habit",
            0
        );

        return;
    }


    let somaPercentual = 0;


    metas.forEach(meta => {

        let percentual =
            (meta.atual /
            meta.alvo) *
            100;


        percentual =
            Math.max(
                0,
                Math.min(
                    100,
                    percentual
                )
            );


        somaPercentual +=
            percentual;

    });


    const geral =
        Math.round(
            somaPercentual /
            metas.length
        );


    definirBarra(
        "general",
        geral
    );


    calcularTipo(
        "finance",
        "financeiro"
    );


    calcularTipo(
        "gym",
        "academia"
    );


    calcularTipo(
        "study",
        "estudos"
    );


    calcularTipo(
        "habit",
        "habitos"
    );

}



/* =========================
   PROGRESSO POR CATEGORIA
========================= */

function calcularTipo(
    prefixo,
    tipo
){

    const lista =
        metas.filter(
            meta =>
                meta.tipo === tipo
        );


    if(lista.length === 0){

        definirBarra(
            prefixo,
            0
        );

        return;
    }


    let total = 0;


    lista.forEach(meta => {

        let percentual =
            (meta.atual /
            meta.alvo) *
            100;


        percentual =
            Math.max(
                0,
                Math.min(
                    100,
                    percentual
                )
            );


        total +=
            percentual;

    });


    const resultado =
        Math.round(
            total /
            lista.length
        );


    definirBarra(
        prefixo,
        resultado
    );

}



/* =========================
   ATUALIZAR BARRA
========================= */

function definirBarra(
    prefixo,
    percentual
){

    const valor =
        Math.round(
            percentual
        );


    const idsTexto = {

        general:"generalPercent",

        finance:"financeProgress",

        gym:"gymProgress",

        study:"studyProgress",

        habit:"habitProgress"

    };


    const texto =
        document.getElementById(
            idsTexto[prefixo]
        );


    const barra =
        document.getElementById(
            prefixo + "Bar"
        );


    if(texto){

        texto.textContent =
            valor + "%";

    }


    if(barra){

        barra.style.width =
            valor + "%";

    }

}



/* =========================
   LIMPAR FORMULÁRIO
========================= */

function limparFormulario(){

    document.getElementById(
        "goalName"
    ).value = "";


    document.getElementById(
        "goalType"
    ).value =
        "financeiro";


    document.getElementById(
        "goalTarget"
    ).value = "";


    document.getElementById(
        "goalCurrent"
    ).value = "";

}



/* =========================
   DESAFIO 7 DIAS
========================= */

function renderizarDesafio(){

    const container =
        document.getElementById(
            "challengeDays"
        );


    container.innerHTML = "";


    desafio.forEach(
        (feito,index) => {


            const dia =
                document.createElement(
                    "div"
                );


            dia.className =
                "day" +
                (feito
                    ? " done"
                    : ""
                );


            dia.innerHTML =
                feito
                ? `✓<br>Dia ${index + 1}`
                : `Dia ${index + 1}`;


            dia.onclick = () => {


                desafio[index] =
                    !desafio[index];


                localStorage.setItem(
                    "pn_desafio",
                    JSON.stringify(
                        desafio
                    )
                );


                renderizarDesafio();

            };


            container.appendChild(
                dia
            );

        }
    );

}



/* =========================
   CONTEÚDOS
========================= */

function abrirConteudo(
    titulo,
    texto
){

    document.getElementById(
        "modalTitle"
    ).textContent =
        titulo;


    document.getElementById(
        "modalText"
    ).textContent =
        texto;


    document.getElementById(
        "modal"
    ).classList.add(
        "show"
    );

}


function fecharConteudo(){

    document.getElementById(
        "modal"
    ).classList.remove(
        "show"
    );

}


document.getElementById(
    "modal"
).addEventListener(
    "click",
    function(event){

        if(
            event.target === this
        ){

            fecharConteudo();

        }

    }
);



/* =========================
   SEGURANÇA DO TEXTO
========================= */

function escaparHTML(texto){

    return String(texto)

        .replace(
            /&/g,
            "&amp;"
        )

        .replace(
            /</g,
            "&lt;"
        )

        .replace(
            />/g,
            "&gt;"
        )

        .replace(
            /"/g,
            "&quot;"
        )

        .replace(
            /'/g,
            "&#039;"
        );

}



/* =========================
   FORMATAÇÃO
========================= */

function formatarNumero(
    numero
){

    return Number(
        numero
    ).toLocaleString(
        "pt-BR",
        {
            maximumFractionDigits:2
        }
    );

}



/* =========================
   INICIAR SITE
========================= */

renderizarMetas();

renderizarDesafio();

</script>

</body>
</html>