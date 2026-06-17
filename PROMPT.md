Edite o index.html da Espetaria Altas Horas. Objetivo: simplificar a seção 
de cardápio removendo as tabs e reorganizando em duas faixas fixas e limpas.

## 1. REMOVER COMPLETAMENTE

Apague todo o bloco das tabs e todos os menu-panels:
- <div class="tabs reveal" role="tablist"> ... </div>
- <div class="menu-panel active" id="panel-espetos"> ... </div>
- <div class="menu-panel" id="panel-pratos"> ... </div>
- <div class="menu-panel" id="panel-adega"> ... </div>
- <div class="menu-panel" id="panel-fds"> ... </div>

Remova também o JS das tabs (o bloco que tem querySelectorAll('.tab') e 
addEventListener para trocar painéis).

## 2. SUBSTITUIR POR DUAS FAIXAS FIXAS

Logo após o quadro-negro, insira este HTML:

<!-- FAIXA ALMOÇO -->
<div class="cardapio-faixa reveal">
  <div class="faixa-header">
    <span class="faixa-tag faixa-almoco">☀️ ALMOÇO</span>
    <span class="faixa-horario">Seg–Sex a partir das 11h30</span>
  </div>
  <div class="cardapio-lista">
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Baião de Dois</span>
        <span class="item-desc">Prato nordestino cremoso com tempero da casa</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20pedir%20Baião%20de%20Dois" target="_blank" rel="noopener">Pedir</a>
    </div>
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Feijão Tropeiro</span>
        <span class="item-desc">Com torresmo, couve refogada e ovo</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20pedir%20Feijão%20Tropeiro" target="_blank" rel="noopener">Pedir</a>
    </div>
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Franguinho à Parmegiana</span>
        <span class="item-desc">Filé de frango com molho e queijo derretido</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20pedir%20Franguinho%20à%20Parmegiana" target="_blank" rel="noopener">Pedir</a>
    </div>
    <div class="cardapio-item destaque-especial">
      <div class="item-info">
        <span class="item-nome">Quarta e Sábado — Feijoadinha 🫘</span>
        <span class="item-desc">Especial da casa, disponível apenas nesses dias</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20saber%20da%20Feijoadinha" target="_blank" rel="noopener">Pedir</a>
    </div>
    <div class="cardapio-item destaque-especial">
      <div class="item-info">
        <span class="item-nome">Domingo — Frango Assado 🍗</span>
        <span class="item-desc">O famoso. A partir das 11h, enquanto durar</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20reservar%20o%20Frango%20Assado%20de%20Domingo" target="_blank" rel="noopener">Reservar</a>
    </div>
  </div>
</div>

<!-- FAIXA ESPETOS -->
<div class="cardapio-faixa reveal">
  <div class="faixa-header">
    <span class="faixa-tag faixa-noite">🔥 ESPETOS & NOITE</span>
    <span class="faixa-horario">Todos os dias • Espetinho R$ 5,00</span>
  </div>
  <div class="cardapio-lista">
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Espetinho Tradicional</span>
        <span class="item-desc">Carne, frango, coração ou queijo — direto da brasa</span>
      </div>
      <div class="item-preco-wrap">
        <span class="item-preco">R$ 5,00</span>
        <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20pedir%20Espetinho" target="_blank" rel="noopener">Pedir</a>
      </div>
    </div>
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Costela na Brasa</span>
        <span class="item-desc">Assada lentamente, suculenta, cheiro de churrasco</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20saber%20o%20valor%20da%20Costela" target="_blank" rel="noopener">Consultar</a>
    </div>
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Combo 5 Espetos</span>
        <span class="item-desc">Cinco espetos variados pra dividir com a galera</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20o%20Combo%20de%205%20Espetos" target="_blank" rel="noopener">Pedir</a>
    </div>
    <div class="cardapio-item">
      <div class="item-info">
        <span class="item-nome">Bebidas & Adega</span>
        <span class="item-desc">Cervejas geladas, refrigerantes, caldos quentes à noite</span>
      </div>
      <a class="item-pedir" href="https://wa.me/5511970121983?text=Olá!%20Quero%20ver%20as%20bebidas" target="_blank" rel="noopener">Ver opções</a>
    </div>
  </div>
</div>

## 3. CSS A ADICIONAR (dentro do <style>)

.cardapio-faixa {
  margin-bottom: 32px;
  border: 1px solid rgba(212,160,23,.2);
  border-top: 2px solid var(--red);
}

.faixa-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 14px 20px;
  background: rgba(204,26,26,.08);
  border-bottom: 1px solid rgba(212,160,23,.15);
}

.faixa-tag {
  font-family: 'Cinzel', serif;
  font-size: .75rem;
  letter-spacing: 3px;
  font-weight: 700;
}

.faixa-almoco { color: var(--gold); }
.faixa-noite { color: var(--orange); }

.faixa-horario {
  font-family: 'IM Fell English', serif;
  font-size: .85rem;
  color: #666;
  font-style: italic;
}

.cardapio-lista {
  display: flex;
  flex-direction: column;
}

.cardapio-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 16px 20px;
  border-bottom: 1px solid rgba(255,255,255,.05);
  transition: background .2s ease;
}

.cardapio-item:last-child { border-bottom: none; }

.cardapio-item:hover {
  background: rgba(212,160,23,.04);
}

.cardapio-item.destaque-especial {
  background: rgba(212,160,23,.04);
  border-left: 3px solid var(--gold);
}

.item-info {
  display: flex;
  flex-direction: column;
  gap: 3px;
  flex: 1;
}

.item-nome {
  font-family: 'Cinzel', serif;
  font-size: .9rem;
  letter-spacing: 1px;
  color: var(--white);
  font-weight: 700;
}

.item-desc {
  font-family: 'IM Fell English', serif;
  font-size: .88rem;
  color: #888;
  font-style: italic;
}

.item-preco-wrap {
  display: flex;
  align-items: center;
  gap: 12px;
  flex-shrink: 0;
}

.item-preco {
  font-family: 'Cinzel', serif;
  font-size: 1.1rem;
  color: var(--gold);
  font-weight: 700;
  white-space: nowrap;
}

.item-pedir {
  flex-shrink: 0;
  background: transparent;
  border: 1px solid rgba(212,160,23,.4);
  color: var(--gold);
  padding: 7px 16px;
  font-family: 'Cinzel', serif;
  font-size: .72rem;
  letter-spacing: 2px;
  text-decoration: none;
  transition: all .2s ease;
  white-space: nowrap;
}

.item-pedir:hover {
  background: var(--red);
  border-color: var(--red);
  color: var(--white);
}

@media (max-width: 640px) {
  .faixa-header { flex-direction: column; align-items: flex-start; gap: 4px; }
  .cardapio-item { flex-wrap: wrap; gap: 10px; }
  .item-preco-wrap { width: 100%; justify-content: space-between; }
}

## IMPORTANTE
- Não mexa em nada fora da section#cardapio
- Mantenha o quadro-negro intacto
- Mantenha todos os outros links de WhatsApp do restante do site
- Não mexa no JS do Three.js, status badge, modal