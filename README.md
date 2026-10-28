<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img alt="Bhagyashree Besra — AI/ML Researcher. Computer vision, medical imaging, biometrics, GenAI. Open to Fall 2027 PhD positions and AI/ML research roles." src="assets/banner-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://besrabhagyashree.github.io"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-besrabhagyashree.github.io-33318a?style=for-the-badge&logo=googlechrome&logoColor=white"></a>
  <a href="mailto:bhagyashreebesra@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-bhagyashreebesra%40gmail.com-b53b6d?style=for-the-badge&logo=gmail&logoColor=white"></a>
  <a href="https://orcid.org/0009-0008-6118-7602"><img alt="ORCID 0009-0008-6118-7602" src="https://img.shields.io/badge/ORCID-0009--0008--6118--7602-A6CE39?style=for-the-badge&logo=orcid&logoColor=white"></a>
</p>

I build machine-learning systems for **computer vision, medical imaging and biometrics**, and I work across the modern **GenAI stack**: LLMs, retrieval-augmented generation and agents. I'm most at home with messy, real-world data, where the images are noisy, the labels are scarce and the results have to hold up.

## 🔬 Focus areas

| | |
|---|---|
| **Medical & forensic imaging**<br><sub>Building and curating image datasets, then segmenting and classifying clinical and forensic images.</sub> | **Machine learning for health**<br><sub>Predictive models on clinical and surveillance data, with careful cleaning, validation and analysis.</sub> |
| **Biometrics & identity**<br><sub>Vein-pattern extraction, feature enhancement and robust matching for identity verification.</sub> | **Computer vision**<br><sub>Image enhancement, feature extraction and deep models for real-world imagery.</sub> |
| **Bioinformatics**<br><sub>Pipelines and visualisation for biological and public-health data.</sub> | **LLMs, RAG & evaluation**<br><sub>Retrieval-augmented systems, fine-tuning, agents, and measuring what models actually get right.</sub> |

## 🧭 Approach

**Data** → **Model** → **Evaluate** → **Deploy**

I own the whole pipeline: curating datasets, choosing the right model (classical ML, deep vision or LLM), validating it rigorously, and shipping it as a working app or service.

## 🌙 Current research: sleep EEG-fMRI

![4 studies complete](https://img.shields.io/badge/studies-4%20complete%20·%201%20in%20progress-b53b6d?style=flat-square)
![OpenNeuro, 3 sites](https://img.shields.io/badge/data-OpenNeuro%20·%203%20sites-33318a?style=flat-square)
![Pre-registered](https://img.shields.io/badge/pre--registered-every%20study-33318a?style=flat-square)

**[sleep-eeg-fmri](https://github.com/besrabhagyashree/sleep-eeg-fmri)**: does cleaning EEG recorded inside an MRI scanner matter for reading sleep from it? Five pre-registered studies on public OpenNeuro data. Cleaning did not significantly improve automated sleep staging overall, but without it the classifier partly read the heartbeat instead of the brain, and standard slow-wave detection worked only after cleaning. Now testing whether these findings replicate in independent NIH and Geneva data.

<sub>Python · MNE-Python · EEG artefact removal · YASA · scikit-learn · non-parametric statistics · pre-registration</sub>

## 🧪 Current research: fruit fly connectome routing

![Work in progress](https://img.shields.io/badge/status-work%20in%20progress-b53b6d?style=flat-square)
![FlyWire v783](https://img.shields.io/badge/data-FlyWire%20v783-33318a?style=flat-square)
![139k neurons](https://img.shields.io/badge/neurons-139%2C255-33318a?style=flat-square)

**[fly-connectome-routing](https://github.com/besrabhagyashree/fly-connectome-routing)**: does the adult *Drosophila* brain's exact wiring decide where each sense reaches the brain-to-body neurons, or do its connection statistics explain it? I test the full connectome against degree-matched randomised brains, including new boundary-preserving null models. So far:

- **The brain's edges set how focused each sense is.** Standard randomisation spreads each sense over 6–7× more descending neurons, but when the sensory and descending connections are locked and only the inside wiring is shuffled, ~99.5% of the focus survives (70 randomised brains).
- **The inside wiring sets *which* neurons each sense reaches.** The simulation agrees with Stürner et al.'s 2025 structural map at ρ = 0.65 in the real brain, 0.51 after inside-only shuffling and 0.07 after standard shuffling (35 brains each; no randomised brain matches the real one). Senses with direct routes, like touch, keep their match; smell, humidity and photoreceptors, which travel through more inside layers, lose up to 40% of it.
- **The map itself moves.** Rebuilt Stürner's flow model (reproduces their ranks at ρ 0.91–0.97) and recomputed it on every randomised brain: inside-only shuffles keep about half the real map, standard shuffles almost none, and simulation and map agree best in the real wiring (0.72 vs at most 0.64 across 70 brains).
- Reproduced the Shiu et al. 2024 whole-brain spiking model (r = 0.99) and matched 1,303 of 1,305 descending neurons to the Stürner atlas.

<sub>Python · NumPy/SciPy · network null models · rate and spiking (Brian2) simulation · graph statistics</sub>

## 🏠 Featured build: Raimani Homes operations platform

![In production](https://img.shields.io/badge/status-in%20production-b53b6d?style=flat-square)
![160+ commands](https://img.shields.io/badge/bot%20commands-160%2B-33318a?style=flat-square)
![26 agents](https://img.shields.io/badge/automation%20agents-26-33318a?style=flat-square)
![100+ modules](https://img.shields.io/badge/API%20%26%20service%20modules-100%2B-33318a?style=flat-square)

A complete operations platform for a residential hostel, which I designed, built and operate. Residents, wardens, staff and admins each work through a **role-aware Telegram assistant** backed by a **Flask REST API and MongoDB**, with **scheduled automation agents** that watch the data and act on it without being asked.

- **Enrollment** with admin approval, document checks and generated application PDFs
- **Attendance** windows, streaks, leave tracking and exception handling
- **Payments**: UPI and cash, invoices, late fees and overdue alerts
- **Meals** with QR counter check-in, ratings and monthly billing
- **Facilities**: maintenance workflow with approvals and ratings, plus medicine and stock inventory
- **Live floor plans** rendered to images server-side with headless Chromium
- **Wellbeing screening** using a validated stress scale (PSS-10)
- **Reliability**: self-healing watchdog, health monitoring and daily on-server backups

<sub>Stack: Python · Flask · Gunicorn · MongoDB · Telegram Bot API · headless Chromium · systemd · cron · Linux server ops. Source is private; it handles residents' personal data.</sub>

## 🛠️ Technical skills

**GenAI & LLMs**<br>
![LLMs](https://img.shields.io/badge/LLMs-33318a?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-33318a?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-33318a?style=flat-square&logo=langchain&logoColor=white)
![LlamaIndex](https://img.shields.io/badge/LlamaIndex-33318a?style=flat-square)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-33318a?style=flat-square&logo=huggingface&logoColor=white)
![Fine-tuning](https://img.shields.io/badge/Fine--tuning-33318a?style=flat-square)
![LLM evaluation](https://img.shields.io/badge/LLM%20evaluation-33318a?style=flat-square)
![AI agents](https://img.shields.io/badge/AI%20agents-33318a?style=flat-square)

**ML, vision & data science**<br>
![TensorFlow](https://img.shields.io/badge/TensorFlow-33318a?style=flat-square&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-33318a?style=flat-square&logo=keras&logoColor=white)
![Computer vision](https://img.shields.io/badge/Computer%20vision-33318a?style=flat-square)
![Image processing](https://img.shields.io/badge/Image%20processing-33318a?style=flat-square)
![Biometrics](https://img.shields.io/badge/Biometrics-33318a?style=flat-square)
![Jupyter](https://img.shields.io/badge/Jupyter-33318a?style=flat-square&logo=jupyter&logoColor=white)
![Anaconda](https://img.shields.io/badge/Anaconda-33318a?style=flat-square&logo=anaconda&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-33318a?style=flat-square)
![Statistical modelling](https://img.shields.io/badge/Statistical%20modelling-33318a?style=flat-square)
![GIS](https://img.shields.io/badge/GIS-33318a?style=flat-square)
![Bioinformatics](https://img.shields.io/badge/Bioinformatics-33318a?style=flat-square)

**Languages**<br>
![Python](https://img.shields.io/badge/Python-b53b6d?style=flat-square&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-b53b6d?style=flat-square&logo=r&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-b53b6d?style=flat-square&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-b53b6d?style=flat-square&logo=c&logoColor=white)
![Java](https://img.shields.io/badge/Java-b53b6d?style=flat-square&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-b53b6d?style=flat-square)
![TypeScript](https://img.shields.io/badge/TypeScript-b53b6d?style=flat-square&logo=typescript&logoColor=white)
![LaTeX](https://img.shields.io/badge/LaTeX-b53b6d?style=flat-square&logo=latex&logoColor=white)

**Web, databases & infra**<br>
![React](https://img.shields.io/badge/React-1d1c45?style=flat-square&logo=react&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-1d1c45?style=flat-square&logo=nextdotjs&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-1d1c45?style=flat-square&logo=nodedotjs&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-1d1c45?style=flat-square&logo=mongodb&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-1d1c45?style=flat-square&logo=mysql&logoColor=white)
![Cassandra](https://img.shields.io/badge/Cassandra-1d1c45?style=flat-square&logo=apachecassandra&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-1d1c45?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-1d1c45?style=flat-square&logo=kubernetes&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-1d1c45?style=flat-square&logo=linux&logoColor=white)

---

<p align="center"><sub>🎓 Open to <b>Fall 2027 PhD positions</b> and <b>AI/ML research roles</b> · Full CV available on request</sub></p>
