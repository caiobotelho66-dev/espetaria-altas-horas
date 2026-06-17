Edite o index.html da Espetaria Altas Horas. Mudanças específicas:



\## 1. HERO — Remover texto duplicado, deixar só a logo



Remova completamente o bloco .hero-brand que contém 

brand-fire-line, brand-title (ADEGA / ESPETARIA / ALTAS / HORAS), 

brand-crown e brand-separator.



Mantenha APENAS a imagem da logo, centralizada, com esse CSS:

.hero-logo {

&#x20; width: clamp(180px, 40vw, 280px);

&#x20; height: auto;

&#x20; object-fit: contain;

&#x20; filter: drop-shadow(0 0 40px rgba(204,26,26,0.6)) 

&#x20;         drop-shadow(0 0 80px rgba(232,82,10,0.3));

&#x20; margin-bottom: 32px;

}



\## 2. TIPOGRAFIA — Trocar Bebas Neue e Oswald por fontes com alma



Substitua no <head> o link do Google Fonts por:

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900\&family=Cinzel:wght@700;900\&family=IM+Fell+English:ital@0;1\&family=Inter:wght@400;500;600\&display=swap" rel="stylesheet">



Mapeamento de uso:

\- Títulos de seção (h2.section-title): font-family: 'Cinzel', serif — letra com peso histórico, gravada em pedra

\- h1 do hero: font-family: 'Playfair Display', serif; font-weight:900; font-style:italic

\- Cards (h3.name): font-family: 'Cinzel', serif; font-size:1rem; letter-spacing:2px

\- Subtítulos e descrições: font-family: 'IM Fell English', serif — tem alma de cardápio antigo de boteco

\- Preços: mantenha Inter mas font-weight:700

\- Corpo geral: Inter como está



\## 3. BOTÕES — Quadrados, sem pill, sem game



Substitua em TODO o CSS qualquer border-radius em botões:

\- .cta-main: border-radius: 2px; padding: 20px 48px; letter-spacing:3px; text-transform:uppercase; font-family:'Cinzel',serif; font-size:1rem

\- .nav-cta: border-radius: 2px

\- .btn-mini: border-radius: 2px

\- .tab: border-radius: 2px

\- .btn-submit: border-radius: 2px

\- .combo-card .btn-mini: border-radius: 2px



Remova box-shadow verde dos botões WhatsApp — substitua por:

box-shadow: 4px 4px 0 rgba(0,0,0,0.5);



\## 4. CARDS — Sem border-radius, com borda real



Todos .menu-card, .combo-card, .info-block, .whats-card:

border-radius: 0;

border: 1px solid rgba(212,160,23,.2);

border-left: 3px solid var(--red);



Hover:

border-left-color: var(--gold);

box-shadow: -3px 0 0 var(--gold), 4px 4px 20px rgba(0,0,0,.5);

transform: translateY(-3px);



\## 5. SECTION TITLES — Mais austeros



.section-title {

&#x20; font-family: 'Cinzel', serif;

&#x20; font-size: clamp(1.6rem, 4vw, 2.8rem);

&#x20; font-weight: 900;

&#x20; letter-spacing: 4px;

&#x20; color: var(--white);

&#x20; text-shadow: none;

}

.section-title .under {

&#x20; width: 40px;

&#x20; height: 2px;

&#x20; background: var(--red);

&#x20; margin: 12px auto 0;

&#x20; border-radius: 0;

}



\## 6. DEPOIMENTOS — Tirar o verde, entrar no tema



.whats-card {

&#x20; background: #0d0a08;

&#x20; border: 1px solid rgba(212,160,23,.2);

&#x20; border-radius: 0;

&#x20; border-top: 2px solid var(--red);

}

.whats-bubble {

&#x20; background: #1a1108;

&#x20; color: var(--white);

&#x20; border-radius: 0;

&#x20; border-left: 2px solid var(--gold);

&#x20; padding: 14px 16px;

}

.whats-bubble::after { display:none; }

.whats-name { color: var(--gold); }



\## 7. TABS DO CARDÁPIO — Sem pill



.tab {

&#x20; border-radius: 0;

&#x20; border: 1px solid rgba(212,160,23,.3);

&#x20; padding: 10px 20px;

&#x20; letter-spacing: 2px;

&#x20; font-family: 'Cinzel', serif;

&#x20; font-size: .8rem;

}

.tab.active {

&#x20; background: var(--red);

&#x20; border-color: var(--red);

&#x20; box-shadow: 4px 4px 0 rgba(0,0,0,.4);

}



\## 8. NAVBAR



.nav-brand {

&#x20; font-family: 'Cinzel', serif;

&#x20; letter-spacing: 3px;

&#x20; font-size: .9rem;

}



\## IMPORTANTE

\- Não mexa na lógica JS

\- Não mexa nos links de WhatsApp  

\- Não mexa na estrutura HTML das seções

\- Apenas CSS e a remoção do bloco hero-brand no HTML

