# Calculadora de Infusão de Insulina (UTI)

App estático (HTML + JS + CSS) para **auxiliar** o ajuste da infusão contínua de insulina em UTI, com base em matriz de decisão **glicemia prévia × glicemia atual**.  
Quando a célula traz “% ou mL/h”, aplica-se a **maior mudança absoluta**.  
**1 U ≡ 1 mL.**

> ⚠️ Aviso clínico: ferramenta educativa para auxiliar decisões. Use julgamento clínico, protocolos locais e monitorização. Em hipoglicemia, siga o fluxo institucional (parada, glicose 50% EV, reavaliação etc.).

## 👩‍⚕️ Como usar
1. Abra a página publicada no GitHub Pages (ver seção *Publicação* abaixo).
2. Informe:
   - **Infusão atual (mL/h)**
   - **Glicemia prévia (mg/dL)**
   - **Glicemia atual (mg/dL)**
   - (Opcional) **Arredondamento** para 0,1 / 0,5 / 1 mL/h
3. Clique em **Calcular nova infusão**.

O app:
- Localiza a célula correta (prévia × atual);
- Aplica “manter”, “± mL/h” **ou** “± % ou ± mL/h (prevalece maior)”;
- Em **hipoglicemia** (<100 mg/dL atual), mostra o fluxo e sugere reinício em **50%** da taxa anterior quando ≥140 mg/dL.

## 🧠 Lógica clínica (resumo)
- Eixo X (colunas): **glicemia prévia (mg/dL)**  
  `<100 | 100–140 | 141–180 | 181–200 | 201–250 | 251–300 | 301–400 | >400`
- Eixo Y (linhas): **glicemia atual (mg/dL)**  
  `<100 | 100–140 | 141–180 | 181–200 | 201–250 | 251–300 | 301–400 | >400`
- Em células “% **ou** mL/h”, prevalece a **maior** variação absoluta sobre a taxa atual.

## 🛠️ Desenvolvimento
O app é **single file**: todo o código está no `index.html`.  
Tecnologias: HTML5 + CSS + JavaScript (sem dependências).

Estrutura de pastas:
