# 🎓 Sistema de Recomendação de Cursos Acessíveis da Udemy  
### Projeto Aplicado III – Sistema de Recomendação baseado em Similaridade Semântica

Este projeto tem como objetivo desenvolver um **sistema de recomendação de cursos acessíveis da plataforma Udemy**, voltado especialmente para **estudantes de baixa renda**, utilizando técnicas modernas de machine learning para análise semântica de textos.

### Link da apresentação no youtube: [https://www.youtube.com/watch?v=2lFzmb2ZXtk](https://www.youtube.com/watch?v=2lFzmb2ZXtk)
---

## 📌 1. Contexto

O acesso à educação de qualidade ainda é limitado para parte da população, especialmente estudantes com restrições financeiras. Plataformas como a Udemy oferecem cursos acessíveis, mas o volume de opções pode dificultar a escolha adequada.

Este projeto busca responder à pergunta:

> **“Como facilitar o acesso de estudantes de baixa renda a cursos de qualidade, personalizados aos seus interesses e necessidades?”**

---

## 🎯 2. Objetivos

### **Objetivo Geral**
Criar um sistema capaz de **recomendar cursos acessíveis da Udemy** alinhados ao perfil e interesses de estudantes de baixa renda.

### **Objetivos Específicos**
- Analisar e filtrar cursos acessíveis (≤ USD 20) com alta qualidade (rating ≥ 4.5).  
- Implementar um modelo de embeddings semânticos para mapear os textos dos cursos.  
- Desenvolver um mecanismo de busca vetorial para recomendação baseada em similaridade.  
- Avaliar a eficácia do sistema utilizando métricas de ranking.  

---

## 🧠 3. Referencial Teórico (Resumo)

- **Sistemas de Recomendação:** Filtragem baseada em conteúdo e técnicas híbridas (Ricci et al., 2015).  
- **Embeddings Semânticos:** Uso do modelo **all-mpnet-base-v2**, derivado de transformers, para capturar significado contextual de frases (Reimers & Gurevych, 2019).  
- **Busca Vetorial:** Recuperação de vizinhos mais próximos em espaço de embeddings; uso de **FAISS** é proposto na literatura.  
- **Avaliação de Rankings:** Métricas como **MAP**, **MRR** e **nDCG** são padrão para sistemas Top-N.  
- **Impacto Social:** Recomendação educacional contribui para empregabilidade e inclusão (Li & Kim, 2021).  

---

## 🛠️ 4. Metodologia

### **4.1 Definição do Problema**
Implementar um sistema que recomende cursos da Udemy levando em conta:
- Baixo custo  
- Alta qualidade  
- Similaridade semântica com interesses informados pelo usuário  

---

### **4.2 Coleta de Dados**
- Fonte: **Kaggle — Udemy Courses Dataset**  
- Inclui informações como título, preço, headline, rating e idioma.  

---

### **4.3 Pré-processamento**
Foram mantidas as colunas:

- `ID`
- `Title`
- `Price`
- `Headline`
- `Average Rating`
- `Language`

Foram aplicados os filtros:
- Preço ≤ **USD 20**  
- Nota ≥ **4.5**  
- Idiomas: **Português**, **Inglês**, **Espanhol**  
- Remoção de linhas com `Headline` nulo  

---

### **4.4 Embeddings e Modelo de Similaridade**
- Modelo escolhido: **all-mpnet-base-v2**  
- Justificativa:
  - Captura relações semânticas profundas
  - Bom equilíbrio custo/desempenho
  - Ideal para recomendação baseada em conteúdo

O texto do campo **Headline** foi transformado em vetores para possibilitar comparação por similaridade de cosseno.

---

### **4.5 Implementação do Sistema**
Pipeline:

1. Usuário insere um interesse ou área (ex.: “data science”, “web design”).  
2. A consulta é convertida em embedding.  
3. Similaridade de cosseno compara a consulta com os cursos vetorizados.  
4. O sistema retorna os cursos mais semanticamente próximos.  

## Integrantes:
	•	Bruna Freitas Soares – RA 10441222
	•	Diogo Moreira Poltosi Rezende – RA 10433404
	•	Heverton Valerio de Lima – RA 10348034
	•	João Victor Fontebasso Alves – RA 10441047
