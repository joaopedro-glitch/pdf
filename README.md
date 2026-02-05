<!DOCTYPE html>
<html lang="pt-PT">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ARGUS Watch - Proposta Técnica</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            dark: '#0f172a',
                            primary: '#0ea5e9',
                            secondary: '#10b981',
                            accent: '#f43f5e',
                            surface: '#f8fafc'
                        }
                    },
                    fontFamily: {
                        sans: ['"Plus Jakarta Sans"', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        body { scroll-behavior: smooth; }
        .glass {
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }
        .pdf-content { background-color: #f8fafc; }
        @media print {
            .no-print { display: none !important; }
            .pdf-content { padding-top: 0 !important; }
            section { break-inside: avoid; margin-bottom: 2rem; }
            .page-break { page-break-before: always; }
            input { border: none !important; background: transparent !important; padding: 0 !important; outline: none !important; }
            ::placeholder { color: transparent !important; }
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 font-sans">

    <!-- HEADER -->
    <header class="no-print fixed top-0 w-full z-50 glass border-b border-slate-200">
        <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <div class="w-10 h-10 bg-brand-dark rounded-xl flex items-center justify-center text-white shadow-lg">
                    <i data-lucide="eye" class="w-6 h-6"></i>
                </div>
                <span class="text-2xl font-extrabold tracking-tighter italic">ARGUS<span class="text-brand-primary not-italic text-sm ml-1">WATCH</span></span>
            </div>
            <button onclick="generatePDF()" class="bg-brand-primary text-white px-6 py-2.5 rounded-full text-sm font-bold hover:bg-sky-600 transition-all flex items-center shadow-lg shadow-sky-200">
                <i data-lucide="file-down" class="w-4 h-4 mr-2"></i>
                Gerar PDF
            </button>
        </div>
    </header>

    <div id="capture-area" class="pdf-content pt-24">
        
        <!-- CAPA -->
        <section class="min-h-[75vh] flex flex-col justify-center px-6 relative overflow-hidden">
            <div class="max-w-5xl mx-auto w-full relative z-10 text-center md:text-left">
                <div class="inline-block px-4 py-1.5 mb-8 rounded-full bg-sky-100 text-sky-600 text-xs font-black uppercase tracking-widest">
                    Proposta Técnica • 2026
                </div>
                <h1 class="text-7xl md:text-9xl font-black text-slate-900 leading-[0.85] mb-8 italic">
                    ARGUS<br><span class="text-brand-primary not-italic">WATCH</span>
                </h1>
                <p class="text-2xl text-slate-500 max-w-2xl font-medium leading-relaxed mb-12">
                    Ferramenta para Monitoramento Assistencial, Segurança do Paciente e Controle de Infecções.
                </p>

                <!-- CAIXA DE IDENTIFICAÇÃO (SOLICITADA) -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 p-8 bg-white rounded-[2.5rem] shadow-xl shadow-slate-200/50 border border-slate-100 max-w-2xl">
                    <div class="space-y-1.5">
                        <label class="text-[10px] font-black uppercase tracking-widest text-slate-400">Cliente / Instituição</label>
                        <input type="text" placeholder="Nome do Hospital ou Grupo" class="w-full bg-slate-50 border border-slate-200 rounded-xl px-4 py-3 text-sm font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-brand-primary/20 transition-all">
                    </div>
                    <div class="space-y-1.5">
                        <label class="text-[10px] font-black uppercase tracking-widest text-slate-400">Nº da Proposta</label>
                        <input type="text" placeholder="Ex: #2026-001" class="w-full bg-slate-50 border border-slate-200 rounded-xl px-4 py-3 text-sm font-bold text-slate-700 focus:outline-none focus:ring-2 focus:ring-brand-primary/20 transition-all">
                    </div>
                </div>
            </div>
            <div class="absolute top-1/2 right-0 w-[500px] h-[500px] bg-brand-primary/5 rounded-full blur-[120px] -mr-64"></div>
        </section>

        <!-- 01. SOBRE A BAUMGRATZ CODE -->
        <section id="sobre" class="py-12 px-6">
            <div class="max-w-5xl mx-auto">
                <div class="p-10 md:p-16 bg-brand-dark text-white rounded-[3rem] shadow-2xl relative overflow-hidden">
                    <h3 class="text-sm font-black uppercase text-brand-secondary tracking-[0.2em] mb-8 flex items-center">
                        <i data-lucide="info" class="w-5 h-5 mr-3"></i> 01. Sobre a Baumgratz Code
                    </h3>
                    
                    <div class="grid md:grid-cols-5 gap-12 items-center">
                        <div class="md:col-span-3 space-y-6 text-slate-300 leading-relaxed text-lg text-justify">
                            <p>A <strong>Baumgratz Code</strong> é uma empresa de tecnologia especializada em soluções digitais, com forte aplicação de Inteligência Artificial, automação e análise avançada de dados. Desenvolvemos plataformas que transformam dados assistenciais e operacionais em insights preditivos, apoiando decisões estratégicas, redução de riscos e melhoria contínua da qualidade do cuidado.</p>
                            <p>Atuamos como parceiros estratégicos das instituições de saúde, impulsionando a inovação, a eficiência operacional e a conformidade regulatória, com foco em segurança do paciente, sustentabilidade do negócio e excelência assistencial.</p>
                        </div>
                        <div class="md:col-span-2 grid grid-cols-2 gap-4">
                            <div class="p-6 bg-white/5 rounded-2xl text-center border border-white/10">
                                <div class="text-brand-secondary font-bold text-3xl">IA</div>
                                <div class="text-[10px] uppercase text-slate-400 font-bold tracking-widest mt-2">Preditiva</div>
                            </div>
                            <div class="p-6 bg-white/5 rounded-2xl text-center border border-white/10">
                                <div class="text-brand-primary font-bold text-3xl">DATA</div>
                                <div class="text-[10px] uppercase text-slate-400 font-bold tracking-widest mt-2">Driven</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 02. SUMÁRIO EXECUTIVO -->
        <section id="executivo" class="py-16 px-6 page-break">
            <div class="max-w-5xl mx-auto">
                <div class="p-12 md:p-16 bg-white rounded-[3.5rem] shadow-xl border-l-8 border-brand-primary">
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-8">02. Sumário Executivo</h3>
                    <div class="space-y-6 text-slate-700 leading-relaxed text-lg text-justify">
                        <p>A Baumgratz Code apresenta a proposta para disponibilização do <strong>ARGUS Watch</strong>, uma plataforma corporativa de monitoramento e gestão de riscos assistenciais, que integra recursos de Inteligência Artificial aplicada à prevenção e ao controle de infecções e à Segurança do Paciente.</p>
                        
                        <p>Desenvolvida para apoiar o Controle de Infecção Hospitalar (CCIH) e o Núcleo de Segurança do Paciente (NSP), a solução permite o acompanhamento contínuo de indicadores, a identificação de padrões de risco, o suporte à tomada de decisão e o gerenciamento de investigações de eventos adversos.</p>
                        
                        <p>Além disso, o ARGUS Watch contempla o controle e a validação dos processos de higienização de ambientes, contribuindo para a redução de riscos, a otimização de custos operacionais e o fortalecimento da qualidade assistencial.</p>
                        
                        <p>Por meio de modelos avançados de IA e análise preditiva, o ARGUS Watch transforma grandes volumes de dados assistenciais e operacionais em insights estratégicos, permitindo que o hospital atue de forma preventiva, antecipando eventos críticos que impactam diretamente a qualidade do cuidado, os custos assistenciais e a sustentabilidade da operação.</p>
                        
                        <p class="font-bold text-slate-900 italic">Ao adotar o ARGUS Watch, o hospital passa a operar com uma visão data-driven, substituindo análises reativas por gestão preditiva de riscos, com impacto direto em ROI, eficiência operacional, conformidade regulatória e posicionamento estratégico da instituição frente a órgãos reguladores, operadoras e processos de acreditação.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 03. FUNCIONALIDADES DO SISTEMA -->
        <section id="funcionalidades" class="py-16 px-6 page-break">
            <div class="max-w-6xl mx-auto">
                <div class="mb-12">
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-4">03. Funcionalidades do Sistema</h3>
                    <h2 class="text-4xl font-black text-slate-900 italic text-justify">Solução Integrada de Monitoramento</h2>
                </div>

                <!-- SUB-SECÇÃO: ASSISTENCIAL E CLÍNICO -->
                <div class="mb-14">
                    <h4 class="text-xl font-bold text-brand-dark mb-6 flex items-center">
                        <span class="w-8 h-8 bg-sky-600 text-white rounded-lg flex items-center justify-center mr-3 text-sm font-bold">A</span>
                        Assistencial e Clínico
                    </h4>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-sky-100 text-sky-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="activity" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Atendimentos e Sinais Vitais</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Consulta com filtros avançados e alertas automáticos de alterações clínicas.</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-sky-100 text-sky-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="stethoscope" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Internações e Dispositivos</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Rastreamento de movimentação, tempo de permanência e controle de dispositivos invasivos em uso.</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-sky-100 text-sky-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="scissors" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Módulo de Cirurgias</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Classificação de risco (Potencial, Limpa, etc.) e controle de Infecção de Sítio Cirúrgico (ISC).</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-sky-100 text-sky-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="microscope" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Laboratório e Exames</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Integração laboratorial para resultados de culturas, antibiogramas e histórico microbiológico.</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4 md:col-span-2">
                            <div class="w-10 h-10 bg-sky-100 text-sky-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="pill" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Gestão de Antimicrobianos</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Monitoramento de prescrições.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- SUB-SECÇÃO: CCIH, NSP E HIGIENIZAÇÃO -->
                <div class="mb-14 page-break">
                    <h4 class="text-xl font-bold text-brand-dark mb-6 flex items-center">
                        <span class="w-8 h-8 bg-emerald-600 text-white rounded-lg flex items-center justify-center mr-3 text-sm font-bold">B</span>
                        CCIH, NSP e Higienização
                    </h4>
                    <div class="grid md:grid-cols-2 gap-6">
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="shield-alert" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Controle de Infecções</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Monitoramento de IRAS, PAV, ITU, ICS, de isolamentos (contato, gotícula, aerossol).</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="search" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Segurança do Paciente</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Registo de eventos adversos com upload de documentos e análise de causa raiz.</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="clipboard-list" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Módulo de Bundles</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Monitoramento de cuidado para prevenção (PAV, ITU) e índices de gravidade (SAPS3, SIRS).</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4">
                            <div class="w-10 h-10 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="droplet" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Higienização e Manutenção</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Gerenciamento completo de ambientes, planos de limpeza programada e checklists de verificação.</p>
                            </div>
                        </div>
                        <div class="bg-white p-6 rounded-[2rem] shadow-sm border border-slate-100 flex items-start space-x-4 md:col-span-2">
                            <div class="w-10 h-10 bg-emerald-100 text-emerald-600 rounded-xl flex items-center justify-center shrink-0"><i data-lucide="flask-conical" class="w-5 h-5"></i></div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 italic text-base">Gestão de Produtos Químicos (FISPQ)</h5>
                                <p class="text-xs text-slate-500 mt-2 leading-relaxed">Sistema de acordo com normas GHS, toxicologia, EPIs recomendados e alertas de incompatibilidade.</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- SUB-SECÇÃO: TECNOLOGIA E INFRAESTRUTURA -->
                <div class="mb-10">
                    <h4 class="text-xl font-bold text-brand-dark mb-6 flex items-center">
                        <span class="w-8 h-8 bg-slate-800 text-white rounded-lg flex items-center justify-center mr-3 text-sm font-bold">C</span>
                        Tecnologia e Infraestrutura
                    </h4>
                    <div class="grid md:grid-cols-1 gap-6">
                        <div class="bg-white p-8 rounded-[2.5rem] shadow-sm border border-slate-100 grid md:grid-cols-3 gap-8">
                            <div class="space-y-3 text-justify">
                                <div class="w-10 h-10 bg-slate-100 text-slate-600 rounded-xl flex items-center justify-center"><i data-lucide="folder-up" class="w-5 h-5"></i></div>
                                <h5 class="font-bold text-slate-900 italic text-base">Gestão de Ficheiros</h5>
                                <p class="text-xs text-slate-500 leading-relaxed">Sistema de upload em lote vinculado automaticamente aos eventos.</p>
                            </div>
                            <div class="space-y-3 text-justify">
                                <div class="w-10 h-10 bg-slate-100 text-slate-600 rounded-xl flex items-center justify-center"><i data-lucide="bell-ring" class="w-5 h-5"></i></div>
                                <h5 class="font-bold text-slate-900 italic text-base">Notificações</h5>
                                <p class="text-xs text-slate-500 leading-relaxed">Sistema para envio de alertas e relatórios automáticos por e-mail.</p>
                            </div>
                            <div class="space-y-3 text-justify">
                                <div class="w-10 h-10 bg-slate-100 text-slate-600 rounded-xl flex items-center justify-center"><i data-lucide="fingerprint" class="w-5 h-5"></i></div>
                                <h5 class="font-bold text-slate-900 italic text-base">Segurança da Informação</h5>
                                <p class="text-xs text-slate-500 leading-relaxed">Autenticação e controle de perfis e logs de auditoria.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 04. ESCOPO DE FORNECIMENTO -->
        <section id="escopo" class="py-16 px-6 page-break">
            <div class="max-w-5xl mx-auto">
                <div class="mb-10">
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-4">04. Escopo de Fornecimento</h3>
                    <h2 class="text-3xl font-black text-slate-900 italic">Infraestrutura e Conformidade</h2>
                </div>

                <div class="grid md:grid-cols-1 gap-6">
                    <div class="p-8 bg-white rounded-[2.5rem] shadow-sm border border-slate-100 space-y-6">
                        <div class="flex items-start space-x-4">
                            <div class="w-12 h-12 bg-sky-50 text-sky-600 rounded-2xl flex items-center justify-center shrink-0">
                                <i data-lucide="cloud"></i>
                            </div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 text-lg">Modelo SaaS (Software as a Service)</h5>
                                <p class="text-sm text-slate-600 leading-relaxed mt-1">
                                    A solução ARGUS Watch será disponibilizada no modelo SaaS, incluindo licenciamento de uso, hospedagem em ambiente seguro, atualizações automáticas, backup periódico dos dados e suporte técnico especializado.
                                </p>
                            </div>
                        </div>

                        <div class="flex items-start space-x-4">
                            <div class="w-12 h-12 bg-emerald-50 text-emerald-600 rounded-2xl flex items-center justify-center shrink-0">
                                <i data-lucide="shield-check"></i>
                            </div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 text-lg">Segurança da Informação</h5>
                                <p class="text-sm text-slate-600 leading-relaxed mt-1">
                                    A plataforma adota boas práticas de Segurança da Informação, com controle de acessos, rastreabilidade de operações, proteção dos dados e disponibilidade do ambiente, assegurando a confidencialidade, integridade e disponibilidade das informações.
                                </p>
                            </div>
                        </div>

                        <div class="flex items-start space-x-4">
                            <div class="w-12 h-12 bg-brand-dark text-white rounded-2xl flex items-center justify-center shrink-0">
                                <i data-lucide="user-check"></i>
                            </div>
                            <div class="text-justify">
                                <h5 class="font-bold text-slate-900 text-lg">Conformidade LGPD</h5>
                                <p class="text-sm text-slate-600 leading-relaxed mt-1">
                                    O ARGUS Watch está alinhado às diretrizes da Lei Geral de Proteção de Dados (LGPD), garantindo o tratamento adequado de dados pessoais e sensíveis, com mecanismos de segurança, governança e conformidade regulatória aplicáveis ao setor de saúde.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 05. METODOLOGIA DE IMPLANTAÇÃO E SUPORTE -->
        <section id="metodologia" class="py-16 px-6 page-break">
            <div class="max-w-5xl mx-auto">
                <div class="mb-10">
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-4">05. Metodologia de Implantação e Suporte</h3>
                    <h2 class="text-3xl font-black text-slate-900 italic">Visão Contínua, Decisão Controlada e Avanço Consciente</h2>
                </div>

                <div class="bg-white p-10 rounded-[3rem] shadow-sm border border-slate-100 space-y-10">
                    <div class="space-y-5 text-justify">
                        <p class="text-slate-700 leading-relaxed">
                            A <strong>AGF – Argus Gate Framework</strong> é a metodologia proprietária da Baumgratz Code para condução de projetos complexos com governança objetiva, foco em valor e previsibilidade de resultados.
                        </p>
                        <p class="text-slate-700 leading-relaxed">
                            Inspirada nas melhores práticas do PMI e nos princípios da metodologia Ágil, a AGF organiza o ciclo de vida do projeto por meio de <strong>GATES decisórios</strong>, que funcionam como portas de qualificação obrigatória para a evolução do projeto.
                        </p>
                        <div class="bg-sky-50 p-6 rounded-2xl border-l-4 border-brand-primary text-sm space-y-2">
                            <p class="font-bold text-brand-dark">Cada Gate representa um ponto formal de decisão:</p>
                            <ul class="space-y-1 text-slate-600">
                                <li class="flex items-center"><i data-lucide="check" class="w-4 h-4 mr-2 text-brand-primary"></i> O projeto só avança quando 100% dos critérios de qualificação daquele Gate são atendidos.</li>
                                <li class="flex items-center"><i data-lucide="check" class="w-4 h-4 mr-2 text-brand-primary"></i> Não há avanço parcial, exceções implícitas ou decisões informais.</li>
                            </ul>
                        </div>
                    </div>

                    <div>
                        <h4 class="font-black text-slate-900 uppercase text-xs tracking-widest mb-6">Princípios da AGF</h4>
                        <div class="grid md:grid-cols-3 gap-6">
                            <div class="p-6 bg-slate-50 rounded-2xl border border-slate-100">
                                <h6 class="font-bold text-brand-dark flex items-center mb-2 italic">Visão Contínua</h6>
                                <p class="text-xs text-slate-500 leading-relaxed">Acompanhamento permanente do projeto, com transparência de riscos, dependências e impactos.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-2xl border border-slate-100">
                                <h6 class="font-bold text-brand-dark flex items-center mb-2 italic">Decisão Controlada</h6>
                                <p class="text-xs text-slate-500 leading-relaxed">Avanços sempre baseados em critérios objetivos, evidências e alinhamento entre as partes.</p>
                            </div>
                            <div class="p-6 bg-slate-50 rounded-2xl border border-slate-100">
                                <h6 class="font-bold text-brand-dark flex items-center mb-2 italic">Avanço Consciente</h6>
                                <p class="text-xs text-slate-500 leading-relaxed">Cada etapa só inicia quando existem condições reais de sucesso, protegendo o investimento do cliente.</p>
                            </div>
                        </div>
                    </div>

                    <div class="border-t border-slate-100 pt-8">
                        <h4 class="font-black text-slate-900 uppercase text-xs tracking-widest mb-4">Estrutura de Governança por Gates</h4>
                        <p class="text-sm text-slate-500 mb-8 italic">A AGF cobre o projeto de ponta a ponta, do comercial à sustentação:</p>
                        
                        <div class="relative">
                            <div class="absolute left-4 top-0 bottom-0 w-0.5 bg-slate-200"></div>
                            <div class="space-y-6">
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 1 – Vendas</span>
                                    <span class="text-xs text-slate-500">Decisão consciente de investimento.</span>
                                </div>
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 2 – Arquitetura</span>
                                    <span class="text-xs text-slate-500">Validação técnica e operacional da solução.</span>
                                </div>
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 3 – Transição Interna</span>
                                    <span class="text-xs text-slate-500">Alinhamento interno antes da execução.</span>
                                </div>
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 4 – Onboarding</span>
                                    <span class="text-xs text-slate-500">Kickoff, governança e autorização formal da execução.</span>
                                </div>
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 5 – Implantação</span>
                                    <span class="text-xs text-slate-500">Execução controlada, com fases de iniciação, planejamento, execução, monitoramento e encerramento.</span>
                                </div>
                                <div class="relative pl-10">
                                    <div class="absolute left-2.5 top-1 w-3.5 h-3.5 bg-brand-primary rounded-full ring-4 ring-sky-100"></div>
                                    <span class="font-bold text-brand-dark block italic">Gate 6 – Suporte</span>
                                    <span class="text-xs text-slate-500">Passagem de bastão formal e encerramento do projeto.</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="bg-brand-dark p-8 rounded-[2.5rem] text-white">
                        <h4 class="text-brand-secondary font-black uppercase text-[10px] tracking-widest mb-6">Benefícios para o Cliente</h4>
                        <ul class="grid md:grid-cols-1 gap-3 text-sm">
                            <li class="flex items-center space-x-3 text-slate-300">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-brand-secondary"></i> 
                                <span>Redução de riscos e retrabalho</span>
                            </li>
                            <li class="flex items-center space-x-3 text-slate-300">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-brand-secondary"></i> 
                                <span>Maior previsibilidade de prazo, custo e resultado</span>
                            </li>
                            <li class="flex items-center space-x-3 text-slate-300">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-brand-secondary"></i> 
                                <span>Clareza de papéis, responsabilidades e decisões</span>
                            </li>
                            <li class="flex items-center space-x-3 text-slate-300">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-brand-secondary"></i> 
                                <span>Governança sem burocracia excessiva</span>
                            </li>
                            <li class="flex items-center space-x-3 text-slate-300">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-brand-secondary"></i> 
                                <span>Transparência total ao longo do projeto</span>
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- 06. ANÁLISE DE ROI E INVESTIMENTO -->
        <section id="investimento" class="py-16 px-6 page-break">
            <div class="max-w-5xl mx-auto">
                <div class="mb-12">
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-4">06. Viabilidade e Investimento</h3>
                    <h2 class="text-3xl font-black text-slate-900 italic">Análise de Payback e Custos</h2>
                </div>

                <!-- ROI ANALYSIS CARD -->
                <div class="p-10 bg-white rounded-[3rem] shadow-sm border border-slate-100 mb-8 overflow-hidden relative text-justify">
                    <div class="absolute top-0 right-0 p-8 opacity-10">
                        <i data-lucide="trending-down" class="w-32 h-32 text-brand-secondary"></i>
                    </div>
                    <h4 class="text-xl font-bold text-slate-800 mb-6 flex items-center italic">
                        <i data-lucide="line-chart" class="w-5 h-5 mr-2 text-brand-primary"></i> Eficiência Financeira (ROI)
                    </h4>
                    <div class="space-y-6 text-slate-600 leading-relaxed relative z-10">
                        <p>
                            O investimento anual no sistema de apoio à Comissão de Controle de Infecção Hospitalar (CCIH), integrado ao módulo de NPS, é de <strong>R$ 26.342,88</strong>. 
                        </p>
                        <p>
                            Estudos nacionais demonstram que o custo médio adicional de um paciente que desenvolve infecção relacionada à assistência à saúde (IRAS) pode chegar a <strong>R$ 38.000 por internação</strong>, em razão do aumento do tempo de permanência hospitalar, maior consumo de antimicrobianos, exames complementares e maior complexidade assistencial, conforme evidenciado em publicações da <strong>UFMS</strong> e em estudos econômicos realizados em hospitais brasileiros.
                            <br>
                            <a href="https://repositorio.ufms.br/handle/123456789/2172" target="_blank" class="text-brand-primary underline text-sm">https://repositorio.ufms.br/handle/123456789/2172</a>
                        </p>
                        <p class="font-bold text-brand-dark bg-sky-50 p-6 rounded-2xl border-l-4 border-brand-primary">
                            Dessa forma, a prevenção de uma única infecção hospitalar ao longo de 12 meses é suficiente para gerar retorno financeiro positivo, além de contribuir para:
                        </p>
                        
                        <div class="grid md:grid-cols-2 gap-4 mt-4">
                            <div class="flex items-center space-x-3 text-slate-700 font-medium">
                                <i data-lucide="check-circle" class="text-brand-secondary w-5 h-5"></i> <span>Redução de riscos assistenciais</span>
                            </div>
                            <div class="flex items-center space-x-3 text-slate-700 font-medium">
                                <i data-lucide="check-circle" class="text-brand-secondary w-5 h-5"></i> <span>Melhoria dos indicadores de qualidade</span>
                            </div>
                            <div class="flex items-center space-x-3 text-slate-700 font-medium">
                                <i data-lucide="check-circle" class="text-brand-secondary w-5 h-5"></i> <span>Otimização da ocupação de leitos</span>
                            </div>
                            <div class="flex items-center space-x-3 text-slate-700 font-medium">
                                <i data-lucide="check-circle" class="text-brand-secondary w-5 h-5"></i> <span>Fortalecimento da segurança do paciente</span>
                            </div>
                        </div>

                        <p class="mt-6 italic">
                            Assim, o sistema apresenta rápido payback, passando a gerar economia contínua para a instituição ao longo de sua vigência.
                        </p>
                    </div>
                </div>

                <!-- INVESTMENT TABLES -->
                <div class="grid md:grid-cols-2 gap-8 mb-8">
                    <!-- MÓDULO CCIH -->
                    <div class="bg-brand-dark text-white p-8 rounded-[3rem] shadow-xl relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-32 h-32 bg-brand-primary/10 rounded-full -mr-16 -mt-16"></div>
                        <h4 class="text-brand-primary font-black uppercase text-xs tracking-widest mb-6 italic">Investimento – Módulo CCIH</h4>
                        <div class="space-y-4">
                            <div class="flex justify-between items-end border-b border-white/10 pb-4">
                                <span class="text-slate-400 text-sm">Mensalidade</span>
                                <span class="text-2xl font-black">R$ 1.282,49</span>
                            </div>
                            <div class="flex justify-between items-end border-b border-white/10 pb-4">
                                <span class="text-slate-400 text-sm">Adicional por CNPJ</span>
                                <span class="text-xl font-bold">R$ 320,62</span>
                            </div>
                        </div>
                        <div class="mt-6 space-y-3 text-[10px] text-slate-400 leading-relaxed text-justify italic">
                            <p>Valores referentes à disponibilização do Módulo CCIH no modelo SaaS.</p>
                            <p>Para a utilização do módulo de IA, será cobrado <strong>R$ 2,00 (dois reais) por milhão de tokens excedentes</strong> à franquia de 1.000.000 de tokens.</p>
                        </div>
                    </div>

                    <!-- MÓDULO NSP -->
                    <div class="bg-white p-8 rounded-[3rem] shadow-sm border border-slate-100 relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-32 h-32 bg-slate-50 rounded-full -mr-16 -mt-16"></div>
                        <h4 class="text-brand-primary font-black uppercase text-xs tracking-widest mb-6 italic">Investimento – Módulo NSP</h4>
                        <div class="space-y-4">
                            <div class="flex justify-between items-end border-b border-slate-100 pb-4">
                                <span class="text-slate-500 text-sm">Mensalidade</span>
                                <span class="text-2xl font-black text-slate-900">R$ 912,75</span>
                            </div>
                            <div class="flex justify-between items-end border-b border-slate-100 pb-4">
                                <span class="text-slate-500 text-sm">Adicional por CNPJ</span>
                                <span class="text-xl font-bold text-slate-900">R$ 228,19</span>
                            </div>
                        </div>
                        <div class="mt-6 space-y-3 text-[10px] text-slate-400 leading-relaxed text-justify italic">
                            <p>Valores referentes à disponibilização do Módulo NSP no modelo SaaS.</p>
                            <p>Para a utilização do módulo de IA, será cobrado <strong>R$ 2,00 (dois reais) por milhão de tokens excedentes</strong> à franquia de 1.000.000 de tokens.</p>
                        </div>
                    </div>
                </div>

                <!-- INFO TOKENS IA -->
                <div class="bg-sky-900 text-white p-8 rounded-[2.5rem] shadow-lg shadow-sky-900/20 relative overflow-hidden">
                    <div class="flex items-start space-x-6 relative z-10">
                        <div class="w-14 h-14 bg-sky-400/20 rounded-2xl flex items-center justify-center shrink-0">
                            <i data-lucide="cpu" class="text-sky-400"></i>
                        </div>
                        <div>
                            <h5 class="text-lg font-bold mb-3 italic">Referência Prática sobre IA (Tokens)</h5>
                            <p class="text-sm text-sky-100 leading-relaxed text-justify">
                                Como referência prática, 1.000.000 de tokens correspondem, em média, a aproximadamente <strong>700.000 a 750.000 palavras em português</strong>.
                            </p>
                        </div>
                    </div>
                    <div class="absolute -bottom-12 -right-12 w-48 h-48 bg-white/5 rounded-full"></div>
                </div>
            </div>
        </section>

        <!-- 07. CONDIÇÕES GERAIS -->
        <section id="condicoes" class="py-16 px-6 page-break">
            <div class="max-w-5xl mx-auto">
                <div class="p-10 md:p-14 bg-slate-900 text-white rounded-[3rem] shadow-2xl relative overflow-hidden">
                    <div class="absolute top-0 right-0 w-64 h-64 bg-brand-primary/5 rounded-full -mr-32 -mt-32"></div>
                    
                    <h3 class="text-sm font-black uppercase text-brand-primary tracking-[0.2em] mb-10 flex items-center">
                        <i data-lucide="file-text" class="w-5 h-5 mr-3"></i> 07. Condições Gerais e Encerramento
                    </h3>
                    
                    <div class="grid md:grid-cols-3 gap-10 mb-16">
                        <div class="space-y-3">
                            <h6 class="text-brand-secondary font-black text-[10px] uppercase tracking-[0.2em]">Faturamento</h6>
                            <p class="text-base text-slate-300 font-medium leading-snug">Envio de nota e boleto Bancário.</p>
                        </div>
                        <div class="space-y-3">
                            <h6 class="text-brand-secondary font-black text-[10px] uppercase tracking-[0.2em]">Validade da Proposta</h6>
                            <p class="text-base text-slate-300 font-medium leading-snug">15 dias.</p>
                        </div>
                        <div class="space-y-3">
                            <h6 class="text-brand-secondary font-black text-[10px] uppercase tracking-[0.2em]">Reajuste</h6>
                            <p class="text-base text-slate-300 font-medium leading-snug">Anual seguindo o IPCA.</p>
                        </div>
                    </div>
                    
                    <div class="bg-white/5 p-8 rounded-2xl border border-white/10 mb-12">
                        <p class="text-slate-300 text-lg italic leading-relaxed text-center">
                            "Estamos à disposição para esclarecer dúvidas e iniciar o projeto."
                        </p>
                    </div>

                    <div class="flex flex-col items-center md:items-start space-y-4">
                        <div class="h-px w-48 bg-brand-primary/30"></div>
                        <div class="text-center md:text-left">
                            <p class="text-2xl font-black tracking-tighter italic">BAUMGRATZ CODE <span class="text-brand-primary not-italic text-sm ml-1">LTDA</span></p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- FOOTER -->
        <footer class="py-12 px-6 text-center border-t border-slate-200 mt-12">
            <div class="flex items-center justify-center space-x-2 mb-4">
                <span class="text-xl font-extrabold tracking-tighter italic text-slate-900">ARGUS<span class="text-brand-primary not-italic text-xs ml-1">WATCH</span></span>
            </div>
            <p class="text-slate-400 text-[10px]">
                Proposta Confidencial validada pela Baumgratz Code &copy; 2026. <br>
                Segurança, Integridade e Previsibilidade na Gestão de Riscos Hospitalares.
            </p>
        </footer>
    </div>

    <script>
        lucide.createIcons();

        function generatePDF() {
            const element = document.getElementById('capture-area');
            const opt = {
                margin: [0, 0],
                filename: 'Proposta_ARGUS_Watch_2026.pdf',
                image: { type: 'jpeg', quality: 0.98 },
                html2canvas: { scale: 2, useCORS: true, letterRendering: true },
                jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
            };

            const btn = event.currentTarget;
            btn.innerHTML = '<i class="animate-spin" data-lucide="loader-2"></i>';
            lucide.createIcons();
            btn.disabled = true;

            html2pdf().set(opt).from(element).save().then(() => {
                btn.innerHTML = '<i data-lucide="file-down" class="w-4 h-4 mr-2"></i> Gerar PDF';
                btn.disabled = false;
                lucide.createIcons();
            });
        }
    </script>
</body>
</html>jsPDF: {
    unit: 'px',jsPDF: {
    unit: 'px',
    format: [1200, document.body.scrollHeight]
}

    format: [1200, document.body.scrollHeight]
}
