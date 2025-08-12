<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contabilidade Guimarães</title>
    <style>
        body {
            background: url('https://images.unsplash.com/photo-1519389950473-47ba0277781c?auto=format&fit=crop&w=800&q=80') no-repeat center center fixed;
            background-size: cover;
            color: #222;
            font-family: Arial, sans-serif;
            position: relative;
            min-height: 100vh;
            overflow-x: hidden;
        }
        body::before {
            content: "";
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background: rgba(224,247,250,0.85);
            z-index: 0;
        }
        main, section, footer, h1, h2, p, table, .horarios, .info-extra, .servicos-extra, .depoimentos, .faq {
            position: relative;
            z-index: 1;
        }
        h1, h2 { text-align: center; }
        h1 { font-size: xx-large; margin-top: 30px; }
        h2 { font-size: medium; margin-bottom: 20px; }
        p { text-align: center; max-width: 700px; margin: 0 auto 15px auto; }
        section { margin-top: 40px; }
        table {
            margin: 0 auto;
            border-collapse: collapse;
            width: 80%;
            background: #fff;
            box-shadow: 0 2px 8px rgba(0,0,0,0.07);
            border-radius: 10px;
            overflow: hidden;
        }
        thead tr {
            background-color: #b2ebf2;
        }
        th, td {
            border: 1px solid #ccc;
            padding: 14px;
            text-align: center;
        }
        th {
            font-size: 1.1em;
        }
        tbody tr:hover {
            background-color: #e0f7fa;
            cursor: pointer;
        }
        .horarios {
            margin: 40px auto 0 auto;
            width: 80%;
            max-width: 500px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.07);
            padding: 20px;
        }
        .horarios h3 {
            text-align: center;
            margin-bottom: 18px;
        }
        .horarios ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }
        .horarios li {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            font-size: 1.05em;
            border-bottom: 1px solid #eee;
        }
        .horario-verde {
            color: #228B22;
            font-weight: bold;
        }
        .horario-vermelho {
            color: #d32f2f;
            font-weight: bold;
        }
        .info-extra {
            text-align: center;
            margin: 20px auto 0 auto;
            font-size: 1.08em;
        }
        .confere-verde {
            color: #228B22;
            font-weight: bold;
            font-size: 1.2em;
            vertical-align: middle;
            margin-right: 4px;
        }
        .descricao-servico {
            display: none;
            margin-top: 8px;
            background: #e0f7fa;
            border-radius: 6px;
            padding: 10px;
            font-size: 0.98em;
            text-align: left;
        }
        .servicos-extra {
            margin: 40px auto 0 auto;
            width: 80%;
            max-width: 700px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.07);
            padding: 20px;
        }
        .servicos-extra h3 {
            text-align: center;
            margin-bottom: 18px;
        }
        .servicos-extra ul {
            list-style: disc;
            padding-left: 20px;
        }
        .depoimentos {
            margin: 40px auto 0 auto;
            width: 80%;
            max-width: 700px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.07);
            padding: 20px;
        }
        .depoimentos h3 {
            text-align: center;
            margin-bottom: 18px;
        }
        .depoimento {
            font-style: italic;
            margin-bottom: 16px;
            color: #444;
        }
        .faq {
            margin: 40px auto 0 auto;
            width: 80%;
            max-width: 700px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.07);
            padding: 20px;
        }
        .faq h3 {
            text-align: center;
            margin-bottom: 18px;
        }
        .faq-item {
            margin-bottom: 12px;
        }
        .faq-q {
            font-weight: bold;
            color: #228B22;
        }
        .faq-a {
            margin-left: 10px;
        }
        footer {
            text-align: center;
            margin-top: 40px;
            font-size: 0.9em;
            color: #555;
        }
        @media (max-width: 700px) {
            table, .horarios, .servicos-extra, .depoimentos, .faq { width: 98%; }
            h1 { font-size: 1.5em; }
        }
        /* Mini chat IA */
        #mini-chat-ia {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 9999;
        }
        #mini-chat-ia .chat-box {
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.15);
            width: 320px;
            max-width: 90vw;
        }
        #mini-chat-ia .chat-header {
            background: #228B22;
            color: #fff;
            padding: 10px 16px;
            border-radius: 10px 10px 0 0;
            font-weight: bold;
        }
        #mini-chat-ia #chat-messages {
            height: 180px;
            overflow-y: auto;
            padding: 10px;
            font-size: 0.98em;
        }
        #mini-chat-ia #chat-form {
            display: flex;
            border-top: 1px solid #eee;
        }
        #mini-chat-ia #chat-input {
            flex: 1;
            padding: 8px;
            border: none;
            border-radius: 0 0 0 10px;
            outline: none;
        }
        #mini-chat-ia button {
            background: #228B22;
            color: #fff;
            border: none;
            padding: 0 16px;
            border-radius: 0 0 10px 0;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Contabilidade Guimarães</h1>
    <h2>Serviços de Contabilidade</h2>
    <p>
        Oferecemos serviços de contabilidade para pequenas e médias empresas, incluindo consultoria fiscal, gestão de folha de pagamento e relatórios financeiros. Sou especialista em ajudar empresas a otimizar seus processos contábeis e garantir conformidade com as regulamentações fiscais.
    </p>
    <p>
        Para mais informações, entre em contato conosco pelo telefone <b>55 (66) 9989-3899</b> ou pelo e-mail <b>alexandresilva.contador@gmail.com</b>
    </p>
    <p>
        <b>Endereço:</b> Rua. Manoel Corrêa de Almeida 113 - Cristo Rei, Varzea Grande - MT, 78118-010, Brasil
    </p>
    <div class="info-extra">
        <span class="confere-verde">&#10003;</span> Aceitamos pix &nbsp;&nbsp;
        <span class="confere-verde">&#10003;</span> Estacionamento na rua
    </div>

    <section>
    <h2>Serviços e Preços</h2>
    <table>
        <thead>
            <tr>
                <th>Serviço</th>
                <th>Preço</th>
            </tr>
        </thead>
        <tbody>
            <tr onclick="mostrarDescricao('desc1')">
                <td>Alteração de empresa MEI para ME</td>
                <td>R$ 380,00
                    <div id="desc1" class="descricao-servico">
                        Transforme seu MEI em ME com toda a documentação, orientação e registro nos órgãos competentes.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc2')">
                <td>Imposto de renda pessoa física</td>
                <td>R$ 99,90
                    <div id="desc2" class="descricao-servico">
                        Preenchimento, envio e acompanhamento da declaração de imposto de renda para pessoas físicas.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc3')">
                <td>Emissão de nota fiscal para MEI</td>
                <td>R$ 49,00
                    <div id="desc3" class="descricao-servico">
                        Emissão de nota fiscal eletrônica para microempreendedores individuais, com suporte e orientação.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc4')">
                <td>Abertura de empresa MEI, ME e EPP</td>
                <td>R$ 380,00
                    <div id="desc4" class="descricao-servico">
                        Abertura de empresas com orientação completa, elaboração de documentos e registro nos órgãos oficiais.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc5')">
                <td>Regularizar pendências da empresa MEI, ME e EPP</td>
                <td>R$ 380,00
                    <div id="desc5" class="descricao-servico">
                        Resolução de pendências fiscais, cadastrais e regularização junto à Receita Federal e demais órgãos.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc6')">
                <td>Consultoria empresarial</td>
                <td>R$ 999,00
                    <div id="desc6" class="descricao-servico">
                        Consultoria estratégica para crescimento, organização, planejamento e gestão empresarial.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc7')">
                <td>Consultoria financeira pessoa física</td>
                <td>R$ 380,00
                    <div id="desc7" class="descricao-servico">
                        Orientação financeira personalizada para pessoas físicas, controle de gastos e planejamento financeiro.
                    </div>
                </td>
            </tr>
            <tr onclick="mostrarDescricao('desc8')">
                <td>Formação de preço de custos</td>
                <td>R$ 850,00
                    <div id="desc8" class="descricao-servico">
                        Cálculo e análise detalhada para formação correta de preços e custos, visando lucratividade e competitividade.
                    </div>
                </td>
            </tr>
        </tbody>
    </table>
</section>

    <div class="servicos-extra">
        <h3>Outros Serviços</h3>
        <ul>
            <li>Planejamento tributário personalizado</li>
            <li>Assessoria para declaração de imposto de renda de pessoa jurídica</li>
            <li>Treinamento para emissão de notas fiscais</li>
            <li>Consultoria para abertura de filiais</li>
            <li>Orientação para enquadramento tributário</li>
            <li>Gestão de contratos e documentos empresariais</li>
        </ul>
    </div>

    <div class="depoimentos">
        <h3>Depoimentos de Clientes</h3>
        <div class="depoimento">"Excelente atendimento, rápido e eficiente. Recomendo!" <br><b>- João Silva</b></div>
        <div class="depoimento">"A consultoria financeira me ajudou a organizar minhas contas e investir melhor." <br><b>- Maria Oliveira</b></div>
        <div class="depoimento">"Serviço de abertura de empresa foi muito prático e seguro." <br><b>- Carlos Souza</b></div>
    </div>

    <div class="faq">
        <h3>Perguntas Frequentes</h3>
        <div class="faq-item">
            <span class="faq-q">Vocês parcelam os serviços?</span>
            <span class="faq-a">Sim, alguns serviços podem ser parcelados. Consulte-nos para saber as condições.</span>
        </div>
        <div class="faq-item">
            <span class="faq-q">O atendimento é rápido?</span>
            <span class="faq-a">Sim, nosso atendimento é eficiente e buscamos sempre agilidade para nossos clientes.</span>
        </div>
        <div class="faq-item">
            <span class="faq-q">Posso pagar com Pix?</span>
            <span class="faq-a">Sim, aceitamos Pix como forma de pagamento.</span>
        </div>
        <div class="faq-item">
            <span class="faq-q">Vocês fazem consultoria online?</span>
            <span class="faq-a">Sim, oferecemos consultoria online e presencial.</span>
        </div>
        <div class="faq-item">
            <span class="faq-q">Quais documentos preciso para abrir empresa?</span>
            <span class="faq-a">Os documentos variam conforme o tipo de empresa. Entre em contato para receber a lista completa.</span>
        </div>
    </div>

    <div class="horarios">
        <h3>Horário de Atendimento</h3>
        <ul>
            <li>Segunda-feira: <span class="horario-verde">08:30-11:00  13:00-17:00</span></li>
            <li>Terça-feira: <span class="horario-verde">08:30-11:00  13:00-17:00</span></li>
            <li>Quarta-feira: <span class="horario-verde">08:30-11:00  13:00-17:00</span></li>
            <li>Quinta-feira: <span class="horario-verde">08:30-11:00  13:00-17:00</span></li>
            <li>Sexta-feira: <span class="horario-verde">08:30-11:00  13:00-17:00</span></li>
            <li>Sábado: <span class="horario-vermelho">Fechado</span></li>
            <li>Domingo: <span class="horario-vermelho">Fechado</span></li>
        </ul>
    </div>

    <!-- Mini chat IA -->
    <div id="mini-chat-ia">
        <div class="chat-box">
            <div class="chat-header">
                Chat IA - Contabilidade
            </div>
            <div id="chat-messages"></div>
            <form id="chat-form">
                <input type="text" id="chat-input" placeholder="Digite sua pergunta..." autocomplete="off">
                <button type="submit">Enviar</button>
            </form>
        </div>
    </div>

    <script>
        function mostrarDescricao(id) {
            var el = document.getElementById(id);
            el.style.display = el.style.display === "none" ? "block" : "none";
        }
        console.log("Bem-vindo(a) à Contabilidade Guimarães!");
        alert("Bem-vindo(a) à Contabilidade Guimarães!");
        
        // Mini chat IA - respostas ampliadas
        const respostasIA = {
            "horário": "Nosso horário de atendimento é de segunda a sexta, das 08:30 às 11:00 e das 13:00 às 17:00.",
            "preço": "Você pode consultar todos os preços na tabela de serviços acima.",
            "pix": "Sim, aceitamos pagamento via Pix.",
            "endereço": "Estamos localizados na Rua. Manoel Corrêa de Almeida 113 - Cristo Rei, Varzea Grande - MT.",
            "contato": "Telefone: (66) 9989-3899 | Email: alexandresilva.contador@gmail.com",
            "nota fiscal": "Emitimos nota fiscal para MEI por R$ 49,00.",
            "consultoria": "Oferecemos consultoria empresarial e financeira. Veja os detalhes na tabela de serviços.",
            "abertura": "Realizamos abertura de empresa MEI, ME e EPP por R$ 380,00.",
            "olá": "Olá! Como posso ajudar você?",
            "oi": "Oi! Como posso ajudar?",
            "boa tarde": "Boa tarde! Em que posso ajudar?",
            "bom dia": "Bom dia! Em que posso ajudar?",
            "boa noite": "Boa noite! Em que posso ajudar?",
            "parcelamento": "Sim, oferecemos opções de parcelamento para alguns serviços. Consulte-nos para mais detalhes.",
            "parcelamos": "Sim, você pode parcelar alguns serviços. Fale conosco para saber as condições.",
            "atendimento é rápido": "Sim, nosso atendimento é muito eficiente e buscamos sempre agilidade para nossos clientes.",
            "atendimento rápido": "Sim, prezamos por um atendimento ágil e eficiente.",
            "tempo de atendimento": "O tempo de atendimento depende do serviço, mas buscamos sempre resolver o mais rápido possível.",
            "documentos necessários": "Os documentos necessários variam conforme o serviço. Entre em contato e informe o serviço desejado para receber a lista.",
            "empresa mei": "Prestamos todos os serviços para MEI, incluindo abertura, alteração, emissão de nota fiscal e regularização.",
            "empresa me": "Prestamos todos os serviços para ME, incluindo abertura, alteração, emissão de nota fiscal e regularização.",
            "empresa epp": "Prestamos todos os serviços para EPP, incluindo abertura, alteração, emissão de nota fiscal e regularização.",
            "formas de pagamento": "Aceitamos Pix, transferência bancária e, em alguns casos, parcelamento.",
            "estacionamento": "Temos estacionamento na rua disponível para nossos clientes.",
            "consultoria tributária": "Sim, oferecemos consultoria tributária para empresas e pessoas físicas.",
            "consultoria fiscal": "Sim, oferecemos consultoria fiscal para empresas e pessoas físicas.",
            "ajuda com imposto de renda": "Sim, fazemos o preenchimento e envio da declaração de imposto de renda.",
            "ajuda com nota fiscal": "Sim, emitimos nota fiscal para MEI e outros tipos de empresa.",
            "ajuda com abertura de empresa": "Sim, realizamos todo o processo de abertura de empresa MEI, ME e EPP.",
            "ajuda com pendências": "Sim, regularizamos pendências fiscais e cadastrais para empresas.",
            "ajuda com custos": "Sim, fazemos a formação de preço de custos para seu negócio.",
            "suporte": "Oferecemos suporte completo para nossos clientes, tanto presencial quanto online.",
            "online": "Alguns serviços podem ser realizados online. Consulte-nos para saber mais.",
            "presencial": "Atendemos presencialmente em nosso endereço em Varzea Grande - MT.",
            "consultoria financeira": "Sim, oferecemos consultoria financeira para pessoas físicas e empresas.",
            "empresa aberta": "Sim, ajudamos você a abrir sua empresa de forma rápida e segura.",
            "empresa regularizada": "Sim, regularizamos sua empresa junto aos órgãos competentes.",
            "serviços": "Veja todos os nossos serviços na tabela acima ou pergunte sobre um serviço específico.",
            "contabilidade": "Somos especialistas em contabilidade para pequenas e médias empresas.",
            "como funciona o parcelamento": "O parcelamento pode ser feito via boleto ou cartão, dependendo do serviço. Consulte-nos para detalhes.",
            "quais serviços posso parcelar": "Abertura de empresa, consultoria empresarial e regularização de pendências podem ser parcelados.",
            "posso pagar com cartão": "Sim, aceitamos cartão de crédito para alguns serviços.",
            "tem desconto para empresas novas": "Sim, oferecemos condições especiais para empresas recém-abertas.",
            "fazem atendimento fora do horário": "Atendimentos fora do horário podem ser agendados previamente.",
            "tem suporte por whatsapp": "Sim, atendemos também pelo WhatsApp.",
            "posso agendar uma visita": "Sim, basta entrar em contato para agendar.",
            "tem estacionamento": "Sim, temos estacionamento na rua para clientes.",
            "fazem consultoria para autônomos": "Sim, oferecemos consultoria para autônomos e profissionais liberais.",
            "ajudam com planejamento tributário": "Sim, nosso serviço de planejamento tributário é personalizado.",
            "fazem treinamento para funcionários": "Sim, oferecemos treinamentos em emissão de notas fiscais e rotinas contábeis.",
            "fazem declaração de imposto de renda de pessoa jurídica": "Sim, fazemos a declaração de imposto de renda de pessoa jurídica.",
            "ajudam com enquadramento tributário": "Sim, orientamos sobre o melhor enquadramento tributário para sua empresa.",
            "fazem consultoria para filiais": "Sim, ajudamos na abertura e gestão de filiais.",
            "fazem gestão de contratos": "Sim, auxiliamos na gestão de contratos e documentos empresariais.",
        };

        function respostaIA(pergunta) {
            pergunta = pergunta.toLowerCase();
            for (const chave in respostasIA) {
                if (pergunta.includes(chave)) {
                    return respostasIA[chave];
                }
            }
            return "Desculpe, não entendi sua pergunta. Por favor, tente perguntar sobre horário, preços, parcelamento, atendimento, Pix, nota fiscal, consultoria ou outros serviços.";
        }

        document.getElementById('chat-form').addEventListener('submit', function(e){
            e.preventDefault();
            const input = document.getElementById('chat-input');
            const mensagem = input.value.trim();
            if(!mensagem) return;
            const chat = document.getElementById('chat-messages');
            chat.innerHTML += `<div style="margin-bottom:8px;"><b>Você:</b> ${mensagem}</div>`;
            setTimeout(() => {
                chat.innerHTML += `<div style="margin-bottom:8px;"><b>IA:</b> ${respostaIA(mensagem)}</div>`;
                chat.scrollTop = chat.scrollHeight;
            }, 600);
            input.value = "";
            chat.scrollTop = chat.scrollHeight;
        });
    </script>
    <footer>
        <p>&copy; 2024 Contabilidade Guimarães. Todos os direitos reservados.</p>
        <p>Desenvolvido por Abdi Gabriel, estudante de Web Design e Programação.</p>
    </footer>
    </body>
    </html>
