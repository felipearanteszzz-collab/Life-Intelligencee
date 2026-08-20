# Life Intelligence

Ferramenta de alta performance pessoal — finanças, rotina, treino e autoconhecimento.

## Estrutura do projeto

```
life-intelligence/
├── public/
│   ├── index.html      # App completo (HTML + CSS + JS)
│   ├── manifest.json   # PWA manifest
│   ├── sw.js           # Service Worker
│   ├── icon-192.png    # ⚠️ FALTA CRIAR
│   └── icon-512.png    # ⚠️ FALTA CRIAR
├── firestore.rules     # Regras de segurança do Firestore
├── firebase.json       # Configuração Firebase Hosting
├── package.json
├── .gitignore
└── README.md
```

## Rodar localmente

```bash
npm install
npm run dev
# Acesse http://localhost:3000
```

## Deploy

### GitHub Pages (atual)
Sobe os arquivos da pasta `public/` no repositório.

### Firebase Hosting (recomendado no futuro)
```bash
npm install -g firebase-tools
firebase login
firebase deploy
```

## Firestore — Estrutura de dados

```
/users/{uid}/
  state: string (JSON serializado do estado completo)
  updatedAt: number (timestamp)
```

## Segurança

- Cada usuário só acessa `/users/{seu_uid}`
- Regras validam `request.auth.uid == userId`
- Campos obrigatórios validados nas regras
- XSS sanitizado via função `esc()` no código

## Próximos passos para PWA/Capacitor

- [ ] Criar ícones icon-192.png e icon-512.png
- [ ] Aplicar regras do Firestore (firestore.rules)
- [ ] Migrar para Firebase Hosting
- [ ] Instalar Capacitor quando projeto virar Node completo
- [ ] Contas Apple Developer e Google Play
