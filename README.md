# Doccana – Extension for the Software Engineering Lab course

> Document annotation and analysis platform, based on the open-source Doccano project.

## Summary

1. [Use Cases](#use-cases)  
2. [About Doccana](#about-doccana)  
3. [Installation and Quickstart](#installation-and-quickstart)  
4. [Project Architecture](#project-architecture)  
5. [Directory Structure](#directory-structure)  
6. [Contribution](#contribution)  
7. [License and Citation](#license-and-citation)  
8. [Contact](#contact)  

---

## Use Cases

---

### Theme 1: User Management
- **Daniel** – View User
- **Gonçalo** – Create User
- **Juary** – Delete User
- **Steve** – Edit User

### Theme 2: Management of Disagreements between Annotators
- **Daniel** – Filtering and view based on perspectives
- **Gonçalo** – Associate annotations with specific perspectives
- **Juary** – Generate reports about the influence of perspectives
- **Steve** – Allow annotators to register their perspective

### Theme 3: Management of Annotator Perspectives
- **Daniel** – Side-by-side display of divergent annotations
- **Gonçalo** – Visual marking of disagreements
- **Juary** – Allow discussion about differences directly in the interface
- **Steve** – Record and resolve disagreements

### Theme 4: Collaborative Resolution of Disagreements
*(Annotation Rules and Voting)*
- **Daniel** – View final vote on annotation rules
- **Gonçalo** – Discuss annotation rules in a collaborative environment
- **Juary** – Vote on annotation rules
- **Steve** – Define annotation rules and configure voting
- **Optional**:  
  - View the history of discussions about annotation rules  
  - Configure notifications for new votes

### Theme 5: Disagreement and Perspective Reports
*(Reports)*
- **Daniel** – Produce statistics on annotations with various filters
- **Gonçalo** – Produce report on the history of annotations with various filters
- **Juary** – Produce report on annotators with various filters
- **Steve** – Produce report on annotations with various filters
- **Optional**:  
  - Produce statistics on the history of annotations with various filters  
  - Export report (PDF/CSV)

---

## About Doccana

**Welcome to Doccana**, our modern and intuitive solution for document annotation.  

- **Who we are**  
  We are Daniel Palma, Gonçalo Cordeiro, Juary Neto and Steve Rocha, students of the Software Engineering Lab (LES) at UAlg.  
- **Name explanation**  
  *Doccana* is our personal touch on the original Doccano: we added an “a” in homage to the base project, reinforcing our identity.  
- **Why this project?**  
  We expanded Doccano with academic and professional features, demonstrating our ability to design robust UX and backend systems.  
- **Instructors**  
  This work was proposed and supervised by Paula Ventura and Néstor Cataño.

---

## Installation and Quickstart

### Prerequisites  
- Python 3.8+  
- Node.js 14+ and npm/yarn  
- Docker & Docker Compose (optional)

### 1. Install with pip
```bash
pip install doccana
doccana init
doccana createuser --username admin --password pass
doccana webserver --port 8000
# In another terminal:
doccana task
```
Access at http://localhost:8000/.

### 2. Using Docker
```bash
docker pull doccano/doccano
docker run -d --name doccana \
  -e ADMIN_USERNAME=admin \
  -e ADMIN_EMAIL=admin@example.com \
  -e ADMIN_PASSWORD=pass \
  -p 8000:8000 \
  doccano/doccano
```

### 3. Using Docker Compose
```bash
git clone https://github.com/doccano/doccano.git
cd doccano
cp docker/.env.example docker/.env
# Edit docker/.env as needed
docker-compose -f docker/docker-compose.prod.yml up --build
```

### 4. (Optional) Cloud Deploy
- **Heroku**: click *Deploy to Heroku* on the repository.  
- **AWS**: use the *Launch Stack* button with the CloudFormation template.

---

## Project Architecture

| Module              | Technology                                            | Purpose                                    |
| ------------------- | ----------------------------------------------------- | ------------------------------------------ |
| Backend             | Python 3, Django, DRF, PostgreSQL/SQLite              | REST APIs, authentication, business logic  |
| Frontend            | Vue.js, Nuxt.js, Vuetify                              | Responsive UI, annotation components       |
| Documentation (Docs) | Markdown + MkDocs + Material for MkDocs              | User and developer guide                   |

---

## Directory Structure

```txt
.
├── backend/             # Django REST code
├── frontend/            # Nuxt/Vue.js + Vuetify app
├── docs/                # MkDocs documentation
├── tools/               # Packaging and CI scripts
├── README.md
└── docker/              # Docker configuration
```

---

## Contribution

1. Fork this repository.  
2. Create a branch: `git checkout -b feature/my-idea`.  
3. Implement and test your changes.  
4. Commit: `git commit -m "Add: my-idea"`.  
5. Push and open a Pull Request.  

See the official contribution guide: https://github.com/doccano/doccano/wiki/How-to-Contribute-to-Doccano-Project.

---

## License and Citation

This project extends [Doccano](https://github.com/doccano/doccano) (MIT License).  
Please cite us as:

```tex
@misc{doccana,
  title={{doccana}: Text Annotation Platform},
  author={Hiroki Nakayama and Takahiro Kubo and Junya Kamura and Yasufumi Taniguchi and Xu Liang},
  year={2018},
  url={https://github.com/doccano/doccano}
}
```

---

## Contact

- Daniel Palma – a71177@ualg.pt  
- Gonçalo Cordeiro – a76967@ualg.pt  
- Juary Neto – a76931@ualg.pt  
- Steve Rocha – a76924@ualg.pt  

Thank you for using **Doccana**!
