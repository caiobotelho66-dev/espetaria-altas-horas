No arquivo index.html da Espetaria Altas Horas, adicione um "quadro negro" 
de prato do dia ANTES das tabs do cardápio, dentro da section#cardapio, 
logo após o <p class="section-subtitle">.

## HTML A INSERIR

Cole este bloco entre o <p class="section-subtitle"> e a <div class="tabs">:

<div class="quadro-negro reveal">
  <div class="quadro-header">
    <span class="quadro-icon">🍽️</span>
    <span class="quadro-label">HOJE NO POINT</span>
    <span class="quadro-data" id="quadro-data"></span>
  </div>
  <div class="quadro-body">
    <div class="quadro-turno">
      <span class="turno-tag turno-almoco">☀️ ALMOÇO</span>
      <p class="turno-desc" id="prato-almoco">Baião de Dois • Feijão Tropeiro • Franguinho à Parmegiana</p>
    </div>
    <div class="quadro-divider"></div>
    <div class="quadro-turno">
      <span class="turno-tag turno-noite">🔥 NOITE</span>
      <p class="turno-desc" id="prato-noite">Espetinhos na brasa — carne, frango, coração e queijo</p>
    </div>
  </div>
  <div class="quadro-footer">
    <a href="https://wa.me/5511970121983?text=Oi!%20Qual%20o%20prato%20de%20hoje%3F%20🍽️"
       target="_blank" rel="noopener" class="quadro-cta">
      <i class="fab fa-whatsapp"></i> Perguntar o cardápio de hoje
    </a>
  </div>
</div>

## CSS A ADICIONAR (dentro do <style>, antes do fechamento </style>)

/* QUADRO NEGRO */
.quadro-negro {
  background: #0a0800;
  border: 1px solid rgba(212,160,23,.35);
  border-top: 3px solid var(--gold);
  border-bottom: 3px solid var(--red);
  padding: 28px 32px;
  margin-bottom: 48px;
  position: relative;
}
.quadro-negro::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  background-size: 150px;
  pointer-events: none;
}
.quadro-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
  padding-bottom: 14px;
  border-bottom: 1px solid rgba(212,160,23,.2);
}
.quadro-icon { font-size: 1.2rem; }
.quadro-label {
  font-family: 'Cinzel', serif;
  font-size: .75rem;
  letter-spacing: 5px;
  color: var(--gold);
  font-weight: 700;
  flex: 1;
}
.quadro-data {
  font-family: 'IM Fell English', serif;
  font-size: .85rem;
  color: #666;
  font-style: italic;
}
.quadro-body {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 24px;
  align-items: center;
}
.quadro-turno { display: flex; flex-direction: column; gap: 10px; }
.turno-tag {
  font-family: 'Cinzel', serif;
  font-size: .7rem;
  letter-spacing: 3px;
  font-weight: 700;
  display: inline-block;
  padding: 4px 10px;
  border: 1px solid;
}
.turno-almoco {
  color: #D4A017;
  border-color: rgba(212,160,23,.4);
  background: rgba(212,160,23,.06);
}
.turno-noite {
  color: #E8520A;
  border-color: rgba(232,82,10,.4);
  background: rgba(232,82,10,.06);
}
.turno-desc {
  font-family: 'IM Fell English', serif;
  font-size: 1.05rem;
  color: var(--white);
  line-height: 1.5;
  font-style: italic;
}
.quadro-divider {
  width: 1px;
  height: 60px;
  background: linear-gradient(180deg, transparent, rgba(212,160,23,.3), transparent);
}
.quadro-footer {
  margin-top: 20px;
  padding-top: 16px;
  border-top: 1px solid rgba(212,160,23,.15);
  text-align: center;
}
.quadro-cta {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: #888;
  font-family: 'Cinzel', serif;
  font-size: .75rem;
  letter-spacing: 2px;
  text-decoration: none;
  transition: color .2s ease;
}
.quadro-cta:hover { color: var(--gold); }
.quadro-cta i { color: #25D366; }

@media (max-width: 640px) {
  .quadro-negro { padding: 20px 18px; }
  .quadro-body { grid-template-columns: 1fr; }
  .quadro-divider { width: 60px; height: 1px; margin: 0 auto;
    background: linear-gradient(90deg, transparent, rgba(212,160,23,.3), transparent); }
}

## JS A ADICIONAR (antes do fechamento </script> no final)

// Data no quadro negro
(function quadroData(){
  const el = document.getElementById('quadro-data');
  if(!el) return;
  const dias = ['Domingo','Segunda','Terça','Quarta','Quinta','Sexta','Sábado'];
  const meses = ['Jan','Fev','Mar','Abr','Mai','Jun','Jul','Ago','Set','Out','Nov','Dez'];
  const now = new Date();
  el.textContent = dias[now.getDay()] + ', ' + now.getDate() + ' ' + meses[now.getMonth()];
})();

## COMO ATUALIZAR O PRATO DO DIA

Para mudar o prato do dia basta editar o texto dentro de:
- id="prato-almoco" → pratos do almoço
- id="prato-noite" → o que tem à noite

Exemplo:
<p class="turno-desc" id="prato-almoco">Feijoadinha Especial • Arroz branco • Couve</p>