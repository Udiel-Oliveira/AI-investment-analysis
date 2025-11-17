# 🚀 Guia de Instalação - Sistema de Análise de Investimentos

## Pré-requisitos

- **Python 3.8+** - [Download](https://www.python.org/downloads/)
- **Node.js 16+** - [Download](https://nodejs.org/)
- **Git** - [Download](https://git-scm.com/)
- **Chave API Alpha Vantage** - [Obter gratuitamente](https://www.alphavantage.co/support/#api-key)

---

## 📥 Passo 1: Clonar o Repositório

```bash
git clone https://github.com/seu-usuario/sistema-analise-investimentos.git
cd sistema-analise-investimentos
```

---

## 🐍 Passo 2: Configurar Backend Python

### 2.1 Criar ambiente virtual (recomendado)

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### 2.2 Instalar dependências

```bash
pip install -r requirements.txt
```

### 2.3 Configurar API Key

Edite o arquivo `api_backend.py` na linha 16:

```python
API_KEY = "SUA_CHAVE_AQUI"  # Substitua pela sua chave da Alpha Vantage
```

### 2.4 Testar o backend

```bash
python api_backend.py
```

Se tudo estiver correto, você verá:
```
🚀 Sistema de Análise de Investimentos iniciado
📊 API rodando em http://localhost:5000
```

**Mantenha este terminal aberto!**

---

## 💻 Passo 3: Configurar Frontend Desktop

### 3.1 Abrir novo terminal

Abra um **segundo terminal** na mesma pasta do projeto.

### 3.2 Instalar dependências Node.js

```bash
npm install
```

### 3.3 Iniciar aplicativo desktop

```bash
npm start
```

O aplicativo desktop será aberto automaticamente! 🎉

---

## ✅ Passo 4: Verificar Instalação

### 4.1 Testar adição de ativo

1. Digite `TSLA` no campo "Adicionar Ativo"
2. Clique em "Adicionar"
3. Aguarde o carregamento dos dados

### 4.2 Testar recomendação de IA

1. Clique em "Ver Recomendação" em algum ativo
2. Verifique se aparece a análise com indicadores

### 4.3 Executar testes automatizados

Em um **terceiro terminal**:

```bash
python test_system.py
```

---

## 🔧 Comandos Úteis

### Desenvolvimento

```bash
# Iniciar backend
python api_backend.py

# Iniciar frontend
npm start

# Executar testes
python test_system.py
```

### Build (distribuição)

```bash
# Windows
npm run build:win

# Mac
npm run build:mac

# Linux
npm run build:linux
```

Os arquivos instaláveis estarão na pasta `dist/`

---

## 📦 Estrutura de Pastas

```
sistema-analise-investimentos/
│
├── api_backend.py          # Backend Flask
├── main.js                 # Electron
├── index.html              # Interface
├── package.json            # Config Node
├── requirements.txt        # Dependências Python
├── test_system.py          # Testes
├── INSTALL.md             # Este arquivo
├── README.md              # Documentação
│
├── cache/                 # Cache da API (criado automaticamente)
├── assets/                # Ícones (criar manualmente)
├── node_modules/          # Dependências Node
└── venv/                  # Ambiente virtual Python
```

---

## 🐛 Resolução de Problemas

### Erro: "ModuleNotFoundError: No module named 'flask'"

**Solução:** Ative o ambiente virtual e reinstale as dependências

```bash
# Windows
venv\Scripts\activate
pip install -r requirements.txt

# Linux/Mac
source venv/bin/activate
pip install -r requirements.txt
```

---

### Erro: "Port 5000 is already in use"

**Solução:** Mude a porta no arquivo `api_backend.py` (última linha):

```python
app.run(debug=True, port=5001)  # Mudou para 5001
```

E em `index.html` (linha 285):

```javascript
const API_URL = 'http://localhost:5001/api';  // Mudou para 5001
```

---

### Erro: "npm: command not found"

**Solução:** Instale o Node.js:
- [Download Node.js](https://nodejs.org/)
- Reinicie o terminal após instalação

---

### Erro: "API Key Invalid"

**Solução:** 
1. Verifique se copiou corretamente a chave da Alpha Vantage
2. Confirme que a chave está ativa
3. Aguarde alguns minutos após obter a chave

---

### Frontend não conecta ao backend

**Solução:**
1. Certifique-se de que o backend está rodando (`python api_backend.py`)
2. Verifique se não há firewall bloqueando a porta 5000
3. Teste acessando http://localhost:5000/api/status no navegador

---

## 📊 Limites da API Gratuita

A Alpha Vantage tem os seguintes limites no plano gratuito:
- **5 requisições por minuto**
- **500 requisições por dia**

Para uso profissional, considere o plano pago.

---

## 🎓 Suporte Acadêmico

Este projeto foi desenvolvido para fins educacionais. Para dúvidas:
- Consulte o arquivo README.md
- Entre em contato com o orientador Prof. Vander
- Abra uma issue no GitHub

---

## ✅ Checklist de Instalação

- [ ] Python 3.8+ instalado
- [ ] Node.js 16+ instalado
- [ ] Dependências Python instaladas
- [ ] Dependências Node instaladas
- [ ] API Key configurada
- [ ] Backend iniciado (porta 5000)
- [ ] Frontend iniciado (Electron)
- [ ] Primeiro ativo adicionado com sucesso
- [ ] Testes executados com sucesso

---

**Pronto! Sistema instalado e funcionando! 🚀**

Para documentação completa, consulte o README.md
