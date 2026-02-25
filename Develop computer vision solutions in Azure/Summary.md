# Azure AI Vision, Custom Vision, Video Indexer e Generative AI – Sintesi Strutturata

## 1. Azure Vision – Image Analysis e OCR

Per utilizzare Azure Vision per l’analisi delle immagini (incluso l’OCR), è necessario:

- Disporre di una sottoscrizione Azure.
- Effettuare il provisioning di una risorsa:
  - Azure Vision resource
  - Oppure Foundry Tools resource (in hub/progetto o standalone)

### Endpoint e autenticazione

L’endpoint ha forma:
https://<resource_name>.cognitiveservices.azure.com/

Autenticazione possibile tramite:
- Key-based authentication
- Microsoft Entra ID

### OCR con REST API

Endpoint:
https://<endpoint>/computervision/imageanalysis:analyze?features=read

Parametri principali:
- image URL o dati binari
- language (default: en)

### OCR con Python SDK

Pacchetto:
azure-ai-vision-imageanalysis

Componenti chiave:
- ImageAnalysisClient
- VisualFeatures.READ
- AzureKeyCredential

I risultati:
- Ritornati sincronicamente
- Strutturati in: blocks → lines → words
- Testo disponibile sia a livello di linea sia di parola

---

## 2. Azure Vision Face API

La Face API consente:

### 2.1 Face Detection
Per ogni volto rilevato:
- Face ID (GUID, valido 24h)
- Bounding box

### 2.2 Face Attribute Analysis
Attributi disponibili:
- Head pose (pitch, roll, yaw)
- Glasses (reading, sunglasses, swimming goggles)
- Mask
- Blur
- Exposure
- Noise
- Occlusion
- Accessories
- QualityForRecognition
- Landmark facciali (coordinate dettagliate)

### 2.3 Face Comparison
- Similarity
- Verification (stessa persona in due immagini)

### 2.4 Facial Recognition (Identificazione)

Procedura:
1. Creare un Person Group
2. Aggiungere una Person per individuo
3. Aggiungere volti rilevati (persisted faces)
4. Addestrare il modello

Il modello può:
- Identificare persone
- Verificare identità
- Trovare volti simili

### 2.5 Facial Liveness
Determina se il video è reale o spoofing.

### 2.6 Modelli
- Più versioni disponibili
- Trade-off tra accuratezza e ampiezza funzionalità

---

## 3. Responsible AI e Dati Biometrici

Aspetti critici:

### Data Privacy & Security
- Dati facciali = dati personali sensibili
- Necessaria protezione in training e inferenza

### Transparency
- Informare utenti su uso e accesso ai dati

### Fairness & Inclusiveness
- Evitare bias e discriminazione
- Prevenire utilizzi impropri

---

## 4. Image Classification

### Definizione
Modello che assegna una classe a un’immagine.

Esempi:
- Sistema di checkout automatico
- Classificazione per tipo di frutta

### Tipologie
- Multiclass: una sola classe per immagine
- Multilabel: più classi per immagine

---

## 5. Azure AI Custom Vision

Permette di creare modelli personalizzati per:

- Image classification
- Object detection

### Risorse richieste

1. Training resource
2. Prediction resource

Separazione utile per:
- Distribuzione geografica
- Scalabilità

Ogni risorsa ha:
- Endpoint
- Chiavi di autenticazione

---

## 6. Custom Vision Portal

Accesso:
https://www.customvision.ai/

Funzionalità:
- Creazione progetto
- Upload immagini
- Tagging
- Training
- Valutazione
- Testing
- Publishing

Ogni progetto ha un Project ID.

### SDK

- .NET:
  - Training
  - Prediction
- Python:
  - azure-cognitiveservices-vision-customvision

---

## 7. Object Detection

### Definizione
Identifica:
- Classe oggetto
- Bounding box (posizione)

### Componenti della predizione
- Label
- Coordinate bounding box (Left, Top, Width, Height – proporzionali)

Esempio:
- Left: 0.1
- Top: 0.5
- Width: 0.5
- Height: 0.25

### Labeling

Differenza chiave:

| Image Classification | Object Detection |
|---------------------|-----------------|
| Tag globale         | Tag + regione   |

Strumenti:
- Interfaccia portale
- Smart labeler
- Tool terzi (richiede formato compatibile)

---

## 8. Azure Video Indexer

Permette di estrarre insight da video.

Funzionalità:

- Facial recognition (richiede accesso limitato)
- OCR
- Speech transcription
- Topic extraction
- Sentiment analysis
- Labels
- Content moderation
- Scene segmentation

Disponibile portale per:
- Upload
- Analisi
- Visualizzazione

---

## 9. Modelli Multimodali (Microsoft Foundry)

Modelli che supportano:
- Testo
- Immagini
- Talvolta audio

Esempi:
- Phi-4-multimodal-instruct
- GPT-4o
- GPT-4o-mini

### Testing
- Chat playground
- Upload immagine + prompt testuale

---

## 10. Vision-Based Chat Applications

Architettura:

- Connessione a endpoint modello
- Invio messaggi multi-part:
  - Testo
  - Immagine

Capacità:
- Comprensione oggetti
- Ragionamento su immagini
- Interpretazione grafici
- Valutazione condizioni (es. danni)

---

## 11. Image Generation con Microsoft Foundry

### Modello DALL-E

Generazione immagini da prompt testuale.

Applicazioni:
- Marketing
- Illustrazioni
- Loghi
- Visual content personalizzato

---

## 12. Image Generation Playground

Parametri configurabili:

- Resolution:
  - 1024x1024
  - 1792x1024
  - 1024x1792
- Style:
  - natural
  - vivid
- Quality:
  - standard
  - hd

---

## 13. Integrazione via API

### REST o SDK

Parametri principali:

- prompt
- n (DALL-E 3: solo 1)
- size
- quality (optional)
- style (optional)

Risposta:
- URL PNG generata
- Revised prompt ottimizzato

---

# Conclusione

L’ecosistema Azure AI e Microsoft Foundry copre:

- Visione classica (OCR, detection, recognition)
- Modelli personalizzati (Custom Vision)
- Analisi video avanzata
- Modelli multimodali
- Generazione immagini

Include inoltre:
- Architetture API/SDK
- Separazione training/prediction
- Considerazioni di Responsible AI
- Supporto a integrazione in applicazioni enterprise