# 🧠 Sistemas Operacionais — Gerência de Memória

Atividade da disciplina de **Sistemas Operacionais I** na **Fatec Taquaritinga**, com a resolução de exercícios de **gerência de memória**: alocação particionada **estática** e **dinâmica**, fragmentação e as estratégias **First-Fit**, **Best-Fit** e **Worst-Fit**.

✅ **Resolução completa:** [`Gerencia_de_Memoria_Resolucao.docx`](Gerencia_de_Memoria_Resolucao.docx)

---

## 📦 Programas usados

| Programa | SO | A | B | C | D |
|---|:---:|:---:|:---:|:---:|:---:|
| **Tamanho (Kb)** | 38 | 5 | 15 | 21 | 29 |

Memória principal: **128 Kb** · espaço para usuário: 128 − 38 = **90 Kb**

---

## 1️⃣ Alocação particionada estática relocável

Partições fixas de **7, 21, 26 e 36 Kb**.

### Mapa da memória

| Endereço | Conteúdo | Partição | Fragmentação interna |
|:---:|---|:---:|:---:|
| 0 Kb | SO | 38 Kb | — |
| 38 Kb | PA (5 Kb) | 7 Kb | 2 Kb |
| 45 Kb | PB (15 Kb) | 21 Kb | 6 Kb |
| 66 Kb | PC (21 Kb) | 26 Kb | 5 Kb |
| 92 Kb | PD (29 Kb) | 36 Kb | 7 Kb |

| Pergunta | Resposta |
|---|---|
| Fragmentação interna total | **20 Kb** (2 + 6 + 5 + 7) |
| Espaço livre para novos programas | **0 Kb**: todas as partições estão ocupadas |
| O programa E (7 Kb) é alocado? | **Não**, não há partição livre |
| E se A for liberado? | **Sim**, E entra na partição de 7 Kb (38–45 Kb), com **0 Kb** de fragmentação |

> A fragmentação interna existe fisicamente, mas não pode ser usada por outros programas.

---

## 2️⃣ Alocação particionada dinâmica relocável

Sem partições fixas: cada programa recebe **exatamente** o espaço de que precisa.

### Mapa da memória

| Endereço | Conteúdo | Tamanho |
|:---:|---|:---:|
| 0 Kb | SO | 38 Kb |
| 38 Kb | PA | 5 Kb |
| 43 Kb | PB | 15 Kb |
| 58 Kb | PC | 21 Kb |
| 79 Kb | PD | 29 Kb |
| 108 Kb | **Livre** | **20 Kb** |

| Pergunta | Resposta |
|---|---|
| Fragmentação interna | **0 Kb** |
| Espaço livre | **20 Kb** contíguos, a partir de 108 Kb |
| O programa E (7 Kb) é alocado? | **Sim**, em 108 Kb; sobram 13 Kb livres |
| E se A for liberado? | **Sim**, mas no bloco de 20 Kb (108 Kb). O buraco de 5 Kb deixado por A é pequeno demais e vira **fragmentação externa** |

---

## 3️⃣ First-Fit × Best-Fit × Worst-Fit

Partições livres, nesta ordem: **A = 10 Kb · B = 3 Kb · C = 7 Kb · D = 25 Kb · E = 17 Kb · F = 20 Kb**

| Estratégia | Regra |
|---|---|
| **First-Fit** | A **primeira** partição em que o processo cabe |
| **Best-Fit** | A **menor** partição em que o processo cabe (menos sobra) |
| **Worst-Fit** | A **maior** partição livre (mais sobra) |

### Resultados

| Processo | First-Fit | Best-Fit | Worst-Fit |
|:---:|:---:|:---:|:---:|
| **13 Kb** | D (sobra 12) | E (sobra 4) | D (sobra 12) |
| **9 Kb** | A (sobra 1) | A (sobra 1) | D (sobra 16) |
| **5 Kb** | A (sobra 5) | C (sobra 2) | D (sobra 20) |
| **20 Kb** | D (sobra 5) | F (sobra **0**, encaixe perfeito) | D (sobra 5) |

Cada processo foi analisado de forma independente, considerando todas as partições livres.

---

## 🎓 Informações acadêmicas

| | |
|---|---|
| **Instituição** | Fatec Taquaritinga |
| **Curso** | Análise e Desenvolvimento de Sistemas — 3º semestre |
| **Disciplina** | Sistemas Operacionais I |
| **Professora** | Gislaine Cristina da Conceição |
| **Ano** | 2026 |

## 👤 Autor

**Juan Gabriel Pereira Augusto**
GitHub: [@JuanGabrielPereiraAugusto](https://github.com/JuanGabrielPereiraAugusto)
