<div align="center">

  <img src="./img/logo_app.png" alt="TEPO Logo" width="460" style="margin-bottom: 24px;" />

  # TEPO — Trento Energy Portfolio Optimizer

  **Decision Support System per la pianificazione e l'ottimizzazione degli interventi di efficientamento energetico sul patrimonio edilizio del Comune di Trento.**

  *Università degli Studi di Trento — Dipartimento di Ingegneria e Scienza dell'Informazione (DISI)*  
  *Corso di Ingegneria del Software (A.A. 2026/2027) — Iniziativa istituzionale: «100 progetti per il Comune di Trento»*

  <br />

  [![Live Demo on Render](https://img.shields.io/badge/Render-Live%20Demo-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://tepobozza.onrender.com)
  [![Java 21](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
  [![Spring Boot 3](https://img.shields.io/badge/Spring_Boot-3.3.4-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
  [![Google OR-Tools](https://img.shields.io/badge/OR--Tools-CP--SAT_9.11-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://developers.google.com/optimization)
  [![PostgreSQL 16](https://img.shields.io/badge/PostgreSQL-16-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
  [![React 18](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

  <br />

  [**Demo Applicativa Online**](https://tepobozza.onrender.com) &nbsp;|&nbsp; [**Repository Principale (TEPO)**](https://github.com/T-E-P-O/TEPO) &nbsp;|&nbsp; [**Deliverable D1 (Requisiti)**](https://github.com/T-E-P-O/D1) &nbsp;|&nbsp; [**Deliverable D2 (Architettura)**](https://github.com/T-E-P-O/D2) &nbsp;|&nbsp; [**Sandbox (tepobozza)**](https://github.com/T-E-P-O/tepobozza)

</div>

---

## Contesto Istituzionale e Obiettivi del Progetto

La gestione degli investimenti per la transizione ecologica del patrimonio immobiliare pubblico richiede strumenti formali di analisi e supporto alle decisioni. Nel contesto del Comune di Trento, il processo decisionale coinvolge un insieme eterogeneo di edifici municipali (istituti scolastici, complessi sportivi, sedi amministrative, immobili a valenza storica), un catalogo articolato di opzioni di riqualificazione tecnologica (relamping LED, sostituzione serramenti, coibentazione dell'involucro edilizio, pompe di calore, impianti fotovoltaici) e vincoli di bilancio stringenti.

Il sistema **TEPO** (Trento Energy Portfolio Optimizer) formalizza tale problema combinatorio attraverso la Ricerca Operativa (modello Knapsack 0-1 / Programmazione Lineare Intera Binaria), consentendo di individuare la composizione ottima del portafoglio di interventi nel rispetto assoluto dei vincoli tecnici, economici e strutturali.

---

## Principio Architetturale: Confinamento Decisionale

Il sistema adotta un principio architetturale rigoroso fondato sulla separazione delle responsabilità e sul controllo umano obbligatorio (*Human-in-the-Loop*):

> ### Il Principio Fondamentale
> **« L'algoritmo propone. L'utente confronta. L'amministrazione decide. »**
>
> I moduli di assistenza e precompilazione operano esclusivamente in lettura e suggerimento, privi di permessi di scrittura sul modello matematico o sui registri comunali. La risoluzione del portafoglio è affidata al motore deterministico Google OR-Tools, con garanzia di convergenza all'ottimo e riproducibilità certificata tramite hash canonico. La decisione finale resta in capo ai funzionari e agli organi decisionali dell'ente.

---

## Interfaccia Operativa ("Strumento Civico")

L'interfaccia utente adotta il design system editoriale **Strumento Civico**, strutturato su due registri di fruizione a elevata leggibilità e conformi agli standard di accessibilità istituzionale:
- **Registro Relazione**: palette chiara e impaginazione documentale, ottimizzata per revisioni d'ufficio, videoproiezioni e stampa formale di relazioni tecniche.
- **Registro Sala Operativa**: palette scura ad alto contrasto, concepita per sessioni prolungate di analisi dati, calcolo combinatorio e monitoraggio cartografico.

| Dashboard Operativa (Registro Relazione) | Dossier di Risultato con Audit Strip |
|:---:|:---:|
| <img src="./img/dashboard-relazione.png" alt="Dashboard Relazione" width="480" /> | <img src="./img/risultato.png" alt="Dossier Risultato" width="480" /> |
| *Indicatori sintetici, stato del catalogo e percorso decisionale.* | *Hash canonico dello scenario, motivazioni formali e allocazione.* |

| Analisi Differenziale What-If (Scenario A vs B) | Cartografia Territoriale degli Edifici |
|:---:|:---:|
| <img src="./img/confronto.png" alt="Confronto A/B" width="480" /> | <img src="./img/mappa.png" alt="Mappa Edifici Trento" width="480" /> |
| *Scostamenti puntuali (B − A) e confronto matriciale degli interventi.* | *Planimetria interattiva con marcatori proporzionali all'investimento.* |

<div align="center">
  <img src="./img/sensibilita.png" alt="Analisi di Sensibilità Parametrica sul Budget" width="750" />
  <p><em>Analisi di sensibilità parametrica: campionamento del budget da 3 a 51 iterazioni per l'identificazione di interventi stabili, oscillanti ed esclusi.</em></p>
</div>

---

## Organizzazione delle Repository

L'organizzazione GitHub **[T-E-P-O](https://github.com/T-E-P-O)** adotta una rigida suddivisione tra codebase del sistema software e deliverable accademici formalizzati:

| Repository | Descrizione e Contenuto | Stato |
|:---|:---|:---:|
| **[TEPO/TEPO](https://github.com/T-E-P-O/TEPO)** | Repository di produzione del software. Include il backend Java 21 / Spring Boot 3 con Google OR-Tools CP-SAT, il frontend React 18 / TypeScript / Vite, le suite di test automatizzati (119 test backend, 69 frontend) e la configurazione Docker e Render. | Attivo |
| **[TEPO/D1](https://github.com/T-E-P-O/D1)** | Deliverable D1 — Requirements Engineering. Documento accademico LaTeX (64 pagine) sincronizzato con Overleaf, recante specifiche formali dei requisiti funzionali e non funzionali, Use Case, User Stories INVEST, Wireframe e Matrice di Tracciabilità. | Rilasciato |
| **[TEPO/D2](https://github.com/T-E-P-O/D2)** | Deliverable D2 — Architectural Design & Testing. Specifica dell'architettura di sistema, protocollo formale di collaudo e test plan. | In corso |
| **[TEPO/tepobozza](https://github.com/T-E-P-O/tepobozza)** | Repository di integrazione e testing continuo. Ambiente integrato con i 10 rami funzionali didattici consolidati sul ramo principale `main`. | Sincronizzato |
| **[TEPO/D3](https://github.com/T-E-P-O/D3)** | Deliverable D3 — Quality Assurance & Test Verification. Report di collaudo, metriche di copertura del codice e analisi statica. | Pianificato |
| **[TEPO/D4](https://github.com/T-E-P-O/D4)** | Deliverable D4 — Final Handover & User Manuals. Manuale d'uso per il personale tecnico del Comune di Trento e relazione conclusiva. | Pianificato |

---

## Moduli Funzionali del Sistema

### 1. Motore di Ottimizzazione OR-Tools CP-SAT
- Risoluzione esatta del problema combinatorio mediante Programmazione Lineare Intera Binaria (MILP 0-1).
- Gestione integrata di vincoli di budget, mutua esclusione tra interventi ($x_A + x_B \le 1$), prerequisiti tecnologici ($x_A \implies x_{\text{req}}$), tetti massimi di spesa per tipologia edilizia e forzature esplicite (inclusioni/esclusioni vincolate).
- **Procedura di Tie-Break a 4 livelli:**
  1. Massimizzazione dell'obiettivo primario prescelto (risparmio energetico, risparmio economico, abbattimento emissioni CO$_2$);
  2. Minimizzazione del costo complessivo di investimento;
  3. Minimizzazione del numero complessivo di cantieri attivati;
  4. Ordinamento lessicografico deterministico per identificativo univoco.
- Generazione di hash SHA-256 canonico dello scenario per tracciabilità, auditabilità e riproducibilità matematica dei risultati.

### 2. Motore delle Spiegazioni Deterministiche (Reason Codes)
Attribuzione deterministica e locale a ogni intervento candidato del rispettivo codice di motivazione:
- *Selezionato per contributo all'obiettivo primario*;
- *Selezionato in quanto prerequisito tecnologico necessario*;
- *Escluso per incompatibilità con altro intervento selezionato*;
- *Escluso per mancata soddisfazione del prerequisito*;
- *Escluso per superamento del budget residuo o complessivo*;
- *Escluso in quanto non compreso nella combinazione ottima globale*.

### 3. Modulo di Confronto Scenari What-If
- Memorizzazione volatile di due configurazioni alternative (Scenario A e Scenario B).
- Calcolo automatico degli scostamenti differenziali diretti $\Delta = B - A$ su parametri fisici (kWh annui), economici (EUR/anno), ambientali (kg CO$_2$/anno) e gestionali (numero cantieri).
- Visualizzazione tabellare degli interventi aggiunti, rimossi e confermati tra le due ipotesi.

### 4. Analisi di Sensibilità Parametrica
- Variazione sistematica del budget disponibile su griglie configurabili da 3 a 51 punti di campionamento.
- Classificazione analitica degli interventi:
  - **Interventi Stabili (Core):** selezionati con costanza all'interno dell'intervallo analizzato;
  - **Interventi Oscillanti (Swing):** la cui ammissibilità dipende fortemente da variazioni marginali del budget;
  - **Interventi Non Convenienti:** mai selezionati all'interno della finestra di spesa esaminata.

### 5. Assistenza in Linguaggio Naturale Confinata (Human-in-the-Loop)
- Interpretazione delle preferenze operative formulate dall'utente in linguaggio naturale.
- Predisposizione di una bozza di scenario precompilata con applicazione strettamente subordinata alla conferma esplicita dell'operatore.
- Meccanismo di fallback deterministico basato su regole analitiche locali in caso di indisponibilità dei servizi esterni.

---

## Architettura Software e Stack Tecnologico

L'architettura adotta criteri di isolamento dei componenti, tipizzazione statica e garanzia di integrità dei dati:

| Sottosistema | Tecnologia Adottata | Motivazione Tecnica e Trade-off |
|:---|:---|:---|
| **Backend & Solutore** | Java 21, Spring Boot 3.3, Google OR-Tools CP-SAT | Binding industriali stabili per la risoluzione esatta con vincoli logici condizionati (`OnlyEnforceIf`). Garanzia di elevate prestazioni e assenza di approssimazioni euristiche. |
| **Persistenza & Dati** | PostgreSQL 16, Flyway Migrations, JPA/Hibernate | Modello relazionale con vincoli stringenti di integrità referenziale tra edifici, interventi e incompatibilità. Storico migrazioni versionato a codice. |
| **Frontend & Presentazione** | React 18, TypeScript 5.5, Vite, Leaflet | Tipizzazione a tempo di compilazione su strutture dati complesse (matrici di sensibilità, dati territoriali, scostamenti $\Delta$). Routing SPA con reindirizzamento deterministico. |
| **Infrastruttura & Esecuzione** | Docker, Temurin JRE Jammy, Render Cloud | Multi-stage build per la compilazione separata dei sorgenti e produzione di un container unico unificato a ingombro ridotto, compatibile con architetture x86_64 e ARM64. |

---

## Avvio in Ambiente Locale

### Esecuzione tramite Docker Compose (Metodo Consigliato)

Requisiti: **Docker Desktop** (o Docker Engine con plugin Compose) installato e attivo.

```bash
# 1. Clonazione della repository principale
git clone https://github.com/T-E-P-O/TEPO.git
cd TEPO

# 2. Compilazione e avvio dell'infrastruttura completa
docker compose up --build
```

Al completamento della procedura di avvio:
- Applicazione Web: [http://localhost:5173](http://localhost:5173)
- Documentazione API REST (OpenAPI / Swagger UI): [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)
- Endpoint di stato: [http://localhost:8080/api/scenarios/ping](http://localhost:8080/api/scenarios/ping)
- Database PostgreSQL: `localhost:5432` (database: `tepo`, utente: `tepo`, password: `tepo`)

### Esecuzione della Suite di Verifica

```bash
# Esecuzione della suite di test backend (119 unit e integration test)
cd backend
mvn clean test

# Esecuzione della suite di test frontend (69 unit test Vitest)
cd ../frontend
npm test
```

---

## Gruppo di Lavoro — Gruppo Didattico T14

Progetto sviluppato collegialmente da:

- **Mirco Negri** — [@mirconegri](https://github.com/mirconegri)
- **Gabriele Duca** — [@ghebbb](https://github.com/ghebbb)
- **Riccardo Scheda** — [@scheddiee](https://github.com/scheddiee)

---

<div align="center">
  <sub>Università degli Studi di Trento — Dipartimento di Ingegneria e Scienza dell'Informazione (DISI)</sub><br />
  <sub>Corso di Ingegneria del Software (A.A. 2026/2027) — Iniziativa «100 progetti per il Comune di Trento»</sub>
</div>
