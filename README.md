# Notas de aula - React Native - Introdução

## Informações gerais

- **Público alvo**: alunos da disciplina de **Programação orienta a serviços** do curso de [Infoweb](https://diatinf.ifrn.edu.br/cursos/tecnico-em-informatica-para-internet/) na [DIATINF](https://diatinf.ifrn.edu.br/)
- **Professor**: [L A Minora](https://github.com/leonardo-minora/)
- **Objetivo**:
  1. Conceitos iniciais sobre desenvolvimento mobile com react native

---
## Notas de aula

### Sumário

1. [Configurando o GitHub Codespace](#1-configurando-o-github-codespace)
2. [Utilitários e Ambiente no Codespace](#2-utilitários-e-ambiente-no-codespace)
3. [Como Criar uma Aplicação com Expo e React Native](#3-como-criar-uma-aplicação-com-expo-e-react-native)
4. [Como Executar o Aplicativo no Codespace](#4-como-executar-o-aplicativo-no-codespace)
5. [Conceitos Básicos do React que Existem em React Native](#5-conceitos-básicos-do-react-que-existem-em-react-native)

---

## 1. Configurando o GitHub Codespace

### 1.1 O que é GitHub Codespace?

GitHub Codespace é um ambiente de desenvolvimento completo baseado em nuvem, diretamente integrado ao GitHub. Você não precisa instalar nada no seu computador - tudo roda no navegador!

**Vantagens:**
- ✅ Sem instalações complicadas
- ✅ Ambiente pré-configurado
- ✅ Acesso de qualquer computador
- ✅ Não consome recursos do seu PC

### 1.2 Abrindo um Codespace neste Repositório

**Opção 1: Pelo botão do repositório**

1. Acesse o repositório: [infoweb-pos/rn-01-introducao](https://github.com/infoweb-pos/rn-01-introducao)
2. Clique no botão verde **"Code"**
3. Clique na aba **"Codespaces"**
4. Clique em **"Create codespace on main"**

**Opção 2: URL direta**

Você pode abrira diretamente via URL:
```
https://github.dev/infoweb-pos/rn-01-introducao
```

### 1.3 Primeira Vez Abrindo o Codespace

Na primeira vez, o Codespace pode levar alguns minutos para ser criado. Você verá:

1. Uma tela de carregamento
2. O VS Code abrindo no navegador
3. Extensões sendo instaladas automaticamente
4. Terminal disponível na parte inferior

Após tudo estar pronto, o ambiente estará 100% funcional com:
- ✅ Node.js e npm pré-instalados
- ✅ Git configurado
- ✅ Terminal integrado
- ✅ Editor de código completo

---

## 2. Utilitários e Ambiente no Codespace

### 2.1 Verificando as Ferramentas Instaladas

Abra o terminal integrado no Codespace:
- Menu superior: **Terminal** → **New Terminal**
- Ou use o atalho: `Ctrl + ~` (Windows/Linux) ou `Cmd + ~` (Mac)

Verifique se Node.js e npm estão instalados:

```bash
node --version
npm --version
```

Você deve ver versões similares a:
```
v18.17.0
9.6.7
```

### 2.2 Instalando Expo CLI no Codespace

No terminal do Codespace, execute:

```bash
npm install -g expo-cli
```

Verifique a instalação:

```bash
expo --version
```

### 2.3 Verificando o Git

Git já está pré-configurado no Codespace:

```bash
git --version
```

### 2.4 Estrutura do Codespace

Ao abrir o Codespace, você verá:

```
Lado esquerdo (Explorer):
├── arquivos do repositório
├── pasta node_modules (após npm install)
└── arquivos do projeto

Parte superior central:
└── Abas dos arquivos abertos

Terminal (parte inferior):
└── Linha de comando integrada
```

---

## 3. Como Criar uma Aplicação com Expo e React Native

### 3.1 Criando um Novo Projeto no Codespace

No terminal do Codespace, navegue para uma pasta de trabalho:

```bash
cd ~
```

Agora crie um novo projeto Expo:

```bash
expo init meu-primeiro-app
```

### 3.2 Respondendo às Perguntas do Expo

O Expo fará algumas perguntas:

```
? Choose a template:
  › bare
    minimal
    managed
```

**Selecione: `managed`** (pressione as setas e Enter)

O Expo pode perguntar se deseja usar Yarn ou npm. Recomendamos **npm**.

### 3.3 Entrando na Pasta do Projeto

```bash
cd meu-primeiro-app
```

### 3.4 Estrutura do Projeto Criado

Veja a estrutura no Codespace clicando na pasta do projeto no Explorer:

```
meu-primeiro-app/
├── node_modules/        # Dependências do projeto
├── App.js               # Componente principal
├── app.json             # Configurações do Expo
├── package.json         # Informações e dependências
├── package-lock.json    # Versões exatas das dependências
└── .gitignore          # Arquivos ignorados pelo Git
```

### 3.5 Entendendo o App.js

Clique no arquivo `App.js` no Explorer para abrir. Você verá:

```javascript
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Open up App.js to start working on your app!</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

**Explicação:**
- `View`: componente container (similar ao `<div>` do React Web)
- `Text`: componente para exibir texto (sempre use para texto)
- `StyleSheet`: API para criar estilos otimizados
- `styles`: objeto com estilos CSS-in-JS similar ao React Web

### 3.6 Personalizando o App.js

Vamos fazer uma mudança simples. No `App.js`, substitua a linha de `Text` por:

```javascript
<Text>Olá! Meu primeiro app em React Native! 🚀</Text>
```

Salve o arquivo: `Ctrl + S` (Windows/Linux) ou `Cmd + S` (Mac)

---

## 4. Como Executar o Aplicativo no Codespace

### 4.1 Iniciando o Servidor Expo

No terminal do Codespace (dentro da pasta do projeto), execute:

```bash
npm start
```

Você verá uma saída similar a:

```
Starting Expo CLI...

Expo  ready at http://localhost:19000

 ┌──────────────────────────────────────────────────────┐
 │                                                      │
 │  Scan this QR code with Expo Go (Android) or the   │
 │  Camera app (iOS)                                   │
 │                                                      │
 │  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  │
 │  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  │
 │  ▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓▓    │
 │  ▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓  ▓▓▓▓▓    │
 │  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  │
 │                                                      │
 └──────────────────────────────────────────────────────┘

Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
```

### 4.2 Opção 1: Testando no Navegador (Recomendado no Codespace)

No terminal, pressione **`w`** e Enter:

```
Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
w
```

**O que vai acontecer:**

1. Uma nova aba do navegador abrirá automaticamente
2. Você verá seu app rodando em um simulador visual
3. Cada mudança no código será refletida automaticamente (hot reload)

**Isso é perfeito para testar no Codespace!**

### 4.3 Testando Mudanças no Código (Hot Reload)

Com o app rodando no navegador:

1. Abra o arquivo `App.js` no Codespace
2. Mude o texto de qualquer componente `<Text>`
3. Salve o arquivo (`Ctrl + S`)
4. **Automaticamente** a mudança aparecerá no navegador sem recarregar

**Exemplo:**

Mude de:
```javascript
<Text>Olá! Meu primeiro app em React Native! 🚀</Text>
```

Para:
```javascript
<Text>React Native é incrível! 💻📱</Text>
```

Salve e veja a mudança aparecer no simulador!

### 4.4 Opção 2: Testando no Celular Físico (Opcional)

Se quiser testar no seu smartphone:

**Passo 1:** Instale o app Expo Go
- Android: [Play Store - Expo Go](https://play.google.com/store/apps/details?id=host.exp.exponent)
- iOS: [App Store - Expo Go](https://apps.apple.com/us/app/expo-go/id982107779)

**Passo 2:** Com o servidor Expo rodando (`npm start`), pressione **`a`** (Android) ou **`i`** (iOS):

```
Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
a
```

**Passo 3:** Escaneie o QR code com seu smartphone:
- **Android**: use o Expo Go
- **iOS**: use a câmera nativa ou Expo Go

### 4.5 Parando o Servidor

Para parar o servidor Expo, pressione `Ctrl + C` no terminal.

### 4.6 Atalhos Úteis do Terminal Expo

Enquanto o servidor está rodando:

| Tecla | Ação |
|-------|------|
| `w` | Abrir no navegador |
| `a` | Abrir em emulador Android |
| `i` | Abrir em emulador iOS |
| `r` | Recarregar app |
| `m` | Mostrar menu de mais opções |
| `c` | Limpar terminal |
| `q` | Parar servidor |

---

## 5. Conceitos Básicos do React que Existem em React Native

Se você já conhece React Web, muitos conceitos são idênticos ou muito similares. Veja os principais:

### 5.1 Componentes Funcionais e Hooks

**React Web:**
```javascript
import React, { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Contagem: {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
}
```

**React Native:**
```javascript
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <View>
      <Text>Contagem: {count}</Text>
      <Button title="Incrementar" onPress={() => setCount(count + 1)} />
    </View>
  );
}
```

**Diferenças:**
- `<div>` → `<View>`
- `<p>` → `<Text>`
- `<button>` → `<Button>` (ou `<Pressable>` para mais customização)
- `onClick` → `onPress`

### 5.2 State (Estado)

O hook `useState` funciona exatamente igual ao React Web:

```javascript
const [valor, setValor] = useState(valorInicial);
```

**Exemplo completo no Codespace:**

1. Abra o `App.js`
2. Copie este código:

```javascript
import React, { useState } from 'react';
import { StyleSheet, Text, View, Button } from 'react-native';

export default function App() {
  const [contador, setContador] = useState(0);

  return (
    <View style={styles.container}>
      <Text style={styles.titulo}>Contador</Text>
      <Text style={styles.numero}>{contador}</Text>
      <Button 
        title="Incrementar" 
        onPress={() => setContador(contador + 1)} 
      />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
  titulo: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
  },
  numero: {
    fontSize: 48,
    marginBottom: 20,
    color: '#007AFF',
  },
});
```

3. Salve e veja no navegador!

### 5.3 Props

Props são passadas da mesma forma:

```javascript
function Saudacao({ nome }) {
  return <Text>Olá, {nome}!</Text>;
}

// Uso:
<Saudacao nome="Maria" />
```

### 5.4 Ciclo de Vida com useEffect

O hook `useEffect` é idêntico ao React Web:

```javascript
import { useEffect } from 'react';

useEffect(() => {
  console.log('Componente montado');
  
  return () => {
    console.log('Componente desmontado');
  };
}, []); // Dependência vazia
```

### 5.5 Estilos com StyleSheet

**React Web:**
```javascript
const styles = {
  container: {
    display: 'flex',
    alignItems: 'center',
    justifyContent: 'center',
    width: '100%',
    height: '100vh',
  }
};

<div style={styles.container}></div>
```

**React Native:**
```javascript
import { StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
  }
});

<View style={styles.container}></View>
```

**Diferenças principais:**
- Flexbox é padrão em React Native (sem necessidade de `display: 'flex'`)
- Não existem unidades (px, %, etc.) - apenas números
- Algumas propriedades CSS não existem
- Propriedades como `backgroundColor`, `borderRadius`, `padding`, `margin` funcionam similar

**Propriedades de estilo comuns:**

```javascript
const styles = StyleSheet.create({
  box: {
    // Tamanho
    width: 100,
    height: 100,
    
    // Espaçamento
    padding: 10,
    margin: 5,
    
    // Cores
    backgroundColor: '#007AFF',
    borderColor: '#000',
    borderWidth: 1,
    
    // Cantos arredondados
    borderRadius: 10,
    
    // Flexbox
    flex: 1,
    flexDirection: 'row',
    justifyContent: 'center',
    alignItems: 'center',
    
    // Texto
    fontSize: 16,
    fontWeight: 'bold',
    color: '#fff',
  }
});
```

### 5.6 Renderização Condicional

Funciona exatamente como React Web:

```javascript
function Componente({ isVisivel }) {
  return (
    <View>
      {isVisivel && <Text>Visível!</Text>}
      {isVisivel ? <Text>Sim</Text> : <Text>Não</Text>}
    </View>
  );
}
```

### 5.7 Listas com map()

Também funciona igual. **Importante:** use `key` em listas!

```javascript
const itens = ['Item 1', 'Item 2', 'Item 3'];

<View>
  {itens.map((item, index) => (
    <Text key={index}>{item}</Text>
  ))}
</View>
```

**Melhor prática:** use um ID único ao invés de `index`:

```javascript
const itens = [
  { id: 1, nome: 'Item 1' },
  { id: 2, nome: 'Item 2' },
  { id: 3, nome: 'Item 3' },
];

<View>
  {itens.map((item) => (
    <Text key={item.id}>{item.nome}</Text>
  ))}
</View>
```

### 5.8 Context API

O Context API funciona de forma idêntica ao React Web:

```javascript
import { createContext, useContext } from 'react';

const MeuContext = createContext();

export function MeuProvider({ children }) {
  const valor = 'Teste';
  return (
    <MeuContext.Provider value={valor}>
      {children}
    </MeuContext.Provider>
  );
}

// Usando o contexto:
const valor = useContext(MeuContext);
```

### 5.9 Custom Hooks

Você pode criar hooks customizados assim como no React Web:

```javascript
function useContador(inicial = 0) {
  const [count, setCount] = useState(inicial);

  const incrementar = () => setCount(count + 1);
  const decrementar = () => setCount(count - 1);

  return { count, incrementar, decrementar };
}

// Uso:
const { count, incrementar, decrementar } = useContador(10);
```

### 5.10 Componentes vs Elementos

Conceitos idênticos ao React Web:

```javascript
// Componente (função)
function MeuComponente() {
  return <Text>Olá</Text>;
}

// Elemento (resultado de renderizar o componente)
const elemento = <MeuComponente />;
```

### 5.11 Principais Diferenças entre React Web e React Native

| Aspecto | React Web | React Native |
|---------|-----------|--------------|
| **DOM** | Renderiza em HTML | Renderiza em componentes nativos |
| **Styling** | CSS, classes, inline styles | StyleSheet, inline styles apenas |
| **Textos** | Qualquer elemento pode ter texto | Apenas `<Text>` pode ter texto |
| **Containers** | `<div>`, `<section>`, etc. | `<View>` |
| **Imagens** | `<img>` | `<Image>` (requer width/height) |
| **Inputs** | `<input>`, `<textarea>` | `<TextInput>` |
| **Eventos** | `onClick`, `onChange`, etc. | `onPress`, `onChangeText`, etc. |
| **Navegação** | React Router, Next.js | React Navigation (biblioteca) |
| **Pacotes** | npm packages (maioria compatível) | npm packages (algumas incompatíveis) |

### 5.12 Recursos Únicos do React Native

Além dos conceitos compartilhados com React Web, React Native oferece recursos específicos para mobile:

- **AsyncStorage**: armazenamento local de dados
- **Vibration**: fazer o dispositivo vibrar
- **Camera**: acesso à câmera do dispositivo
- **Geolocation**: obter localização GPS
- **Push Notifications**: notificações push
- **Sensor APIs**: acelerômetro, giroscópio, etc.

Esses recursos geralmente requerem bibliotecas adicionais. No Codespace, você pode instalar com:

```bash
npm install expo-camera expo-location expo-notifications
```

### 5.13 Componentes Nativos Comuns

Aqui estão alguns componentes essenciais do React Native:

**View**
```javascript
<View style={{ flex: 1, padding: 10 }}>
  {/* Conteúdo aqui */}
</View>
```

**Text**
```javascript
<Text style={{ fontSize: 16 }}>Meu texto</Text>
```

**Button**
```javascript
<Button 
  title="Pressione-me" 
  onPress={() => console.log('Pressionado!')} 
/>
```

**TextInput**
```javascript
<TextInput
  placeholder="Digite seu nome"
  value={nome}
  onChangeText={setNome}
  style={{ borderWidth: 1, padding: 10 }}
/>
```

**Image**
```javascript
<Image
  source={{ uri: 'https://example.com/image.png' }}
  style={{ width: 100, height: 100 }}
/>
```

**ScrollView**
```javascript
<ScrollView>
  <Text>Conteúdo que pode rolar</Text>
</ScrollView>
```

**FlatList** (para listas eficientes)
```javascript
<FlatList
  data={items}
  renderItem={({ item }) => <Text>{item.name}</Text>}
  keyExtractor={(item) => item.id.toString()}
/>
```

---

## Guia Rápido: Primeiros Passos no Codespace

### Resumo do Fluxo

1. **Abrir Codespace**
   ```
   https://github.dev/infoweb-pos/rn-01-introducao
   ```

2. **Criar projeto**
   ```bash
   cd ~
   expo init meu-app
   cd meu-app
   ```

3. **Iniciar servidor**
   ```bash
   npm start
   ```

4. **Testar no navegador**
   ```
   Pressione 'w' no terminal
   ```

5. **Fazer mudanças**
   - Editar `App.js`
   - Salvar (`Ctrl + S`)
   - Ver mudança automática no navegador

6. **Parar servidor**
   ```
   Pressione Ctrl + C no terminal
   ```

### Dúvidas Comuns

**P: Posso criar múltiplos projetos no Codespace?**
R: Sim! Use diretórios diferentes, ex: `~/meu-app1`, `~/meu-app2`

**P: Onde estão os arquivos depois que fecho o Codespace?**
R: Tudo é automaticamente salvo no repositório GitHub. Ao reabrir, tudo estará lá.

**P: Como faço commit dos meus projetos?**
R: No terminal do Codespace:
```bash
git add .
git commit -m "Meu primeiro app React Native"
git push
```

**P: O Codespace tem limite de tempo?**
R: Sim, mas é bastante generoso para uso educacional. Se ficar muito tempo sem usar, ele pode ser suspenso.

---

## Recursos Úteis

- [Documentação Oficial Expo](https://docs.expo.dev/)
- [Documentação React Native](https://reactnative.dev/docs/getting-started)
- [Componentes React Native](https://reactnative.dev/docs/components-and-apis)
- [GitHub Codespaces - Guia](https://docs.github.com/pt/codespaces)
- [Expo Go - Play Store](https://play.google.com/store/apps/details?id=host.exp.exponent)
- [Expo Go - App Store](https://apps.apple.com/us/app/expo-go/id982107779)

---

## Próximos Passos Sugeridos

1. ✅ Criar seu primeiro projeto no Codespace
2. ✅ Explorar diferentes componentes React Native
3. ✅ Praticar Estado (useState) e Props
4. ✅ Criar uma tela com múltiplos componentes
5. ✅ Usar StyleSheet para estilizar seus apps
6. ✅ Praticar renderização condicional e listas
7. ✅ Integrar React Navigation para múltiplas telas
8. ✅ Explorar APIs nativas do Expo

---
