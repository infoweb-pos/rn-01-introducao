# Notas de aula - React Native - Introdução

## Informações gerais

- **Público alvo**: alunos da disciplina de **Programação orienta a serviços** do curso de [Infoweb](https://diatinf.ifrn.edu.br/cursos/tecnico-em-informatica-para-internet/) na [DIATINF](https://diatinf.ifrn.edu.br/)
- **Professor**: [L A Minora](https://github.com/leonardo-minora/)
- **Objetivo**:
  1. Conceitos iniciais sobre desenvolvimento mobile com react native

---
## Notas de aula

### Sumário

1. [Utilitários Necessários para Desenvolvimento](#1-utilitários-necessários-para-desenvolvimento)
2. [Como Criar uma Aplicação com Expo e React Native](#2-como-criar-uma-aplicação-com-expo-e-react-native)
3. [Como Executar o Aplicativo e Ver o Resultado no Celular](#3-como-executar-o-aplicativo-e-ver-o-resultado-no-celular)
4. [Conceitos Básicos do React que Existem em React Native](#4-conceitos-básicos-do-react-que-existem-em-react-native)

---

## 1. Utilitários Necessários para Desenvolvimento

Para começar a desenvolver aplicações com React Native e Expo, você vai precisar das seguintes ferramentas:

### 1.1 Node.js e npm

**Node.js** é um ambiente de execução JavaScript e **npm** é o gerenciador de pacotes JavaScript.

**Como instalar:**

1. Acesse [nodejs.org](https://nodejs.org/) e baixe a versão LTS (Long Term Support)
2. Execute o instalador e siga os passos de instalação
3. Verifique a instalação abrindo o terminal/prompt de comando e digitando:

```bash
node --version
npm --version
```

### 1.2 Git

**Git** é um sistema de controle de versão essencial para gerenciar seu código.

**Como instalar:**

1. Acesse [git-scm.com](https://git-scm.com/) e baixe a versão para seu sistema operacional
2. Execute o instalador
3. Verifique a instalação:

```bash
git --version
```

### 1.3 Expo CLI

**Expo CLI** é a ferramenta oficial do Expo para criar e gerenciar projetos React Native.

**Como instalar:**

Abra seu terminal/prompt de comando e execute:

```bash
npm install -g expo-cli
```

Verifique a instalação:

```bash
expo --version
```

### 1.4 Editor de Código

Recomendamos um dos seguintes editores:

- **Visual Studio Code (VS Code)**: [code.visualstudio.com](https://code.visualstudio.com/)
- **WebStorm**: [jetbrains.com/webstorm](https://www.jetbrains.com/webstorm/)
- **Sublime Text**: [sublimetext.com](https://www.sublimetext.com/)

Para VS Code, recomendamos instalar as seguintes extensões:
- **ES7+ React/Redux/React-Native snippets** (dsznajder.es7-react-js-snippets)
- **Prettier - Code formatter** (esbenp.prettier-vscode)

### 1.5 Emulador ou Dispositivo Físico (Opcional)

Para testar sua aplicação, você pode usar:

**Opção 1: Emulador Android**
- Instale o [Android Studio](https://developer.android.com/studio)
- Configure um emulador virtual

**Opção 2: Emulador iOS (apenas macOS)**
- Instale o [Xcode](https://apps.apple.com/us/app/xcode/id497799835)
- Use o simulador iOS integrado

**Opção 3: Dispositivo Físico (Recomendado)**
- Instale o app **Expo Go** na Play Store (Android) ou App Store (iOS)
- Use seu smartphone para testar

---

## 2. Como Criar uma Aplicação com Expo e React Native

### 2.1 Criando um Novo Projeto

Abra seu terminal/prompt de comando e execute:

```bash
expo init nome-do-meu-app
```

Você será perguntado qual template deseja usar. Para iniciantes, recomendamos:

```
? Choose a template:
  › bare
    minimal
    managed
```

Selecione **managed** (que inclui Expo pré-configurado).

### 2.2 Navegando até a Pasta do Projeto

```bash
cd nome-do-meu-app
```

### 2.3 Estrutura do Projeto

Após criar o projeto, você verá a seguinte estrutura:

```
nome-do-meu-app/
├── node_modules/        # Dependências do projeto
├── App.js               # Componente principal da aplicação
├── app.json             # Configurações do Expo
├── package.json         # Informações do projeto e dependências
├── package-lock.json    # Versões exatas das dependências
└── .gitignore          # Arquivos ignorados pelo Git
```

### 2.4 Entendendo o App.js

O arquivo `App.js` é o ponto de entrada da sua aplicação. Um exemplo básico:

```javascript
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Olá, React Native!</Text>
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
- `Text`: componente para exibir texto (deve ser usado para todo texto)
- `StyleSheet`: API para criar estilos otimizados
- `styles.container`: estilos CSS-in-JS similar ao React Web

### 2.5 Instalando Dependências Adicionais

Se precisar instalar pacotes npm:

```bash
npm install nome-do-pacote
```

Ou com yarn:

```bash
yarn add nome-do-pacote
```

---

## 3. Como Executar o Aplicativo e Ver o Resultado no Celular

### 3.1 Iniciando o Servidor Expo

Na raiz do seu projeto, execute:

```bash
expo start
```

Ou use o atalho:

```bash
npm start
```

Você verá um terminal interativo com um QR code:

```
 Expo  ready at http://localhost:19000

 ┌──────────────────────────────────────────────────────────────┐
 │                                                              │
 │   Scan this QR code with Expo Go (Android) or the Camera   │
 │   app (iOS)                                                 │
 │                                                              │
 │  [QR Code aqui]                                            │
 │                                                              │
 └──────────────────────────────────────────────────────────────┘

Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
```

### 3.2 Opção 1: Usando Expo Go (Recomendado para Iniciantes)

**Passo 1:** Instale o app **Expo Go**
- Android: [Play Store - Expo Go](https://play.google.com/store/apps/details?id=host.exp.exponent)
- iOS: [App Store - Expo Go](https://apps.apple.com/us/app/expo-go/id982107779)

**Passo 2:** Abra o Expo Go no seu smartphone

**Passo 3:** Aponte a câmera do seu celular para o QR code exibido no terminal

**Passo 4:** O app será carregado automaticamente no seu dispositivo

### 3.3 Opção 2: Usando Emulador Android

**Pré-requisito:** Android Studio instalado e emulador configurado

**Passo 1:** Inicie o emulador Android (via Android Studio)

**Passo 2:** Com o Expo rodando, pressione `a` no terminal

```
Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
a
```

**Passo 3:** O Expo Go será instalado automaticamente e seu app será executado

### 3.4 Opção 3: Usando Emulador iOS (macOS apenas)

**Pré-requisito:** Xcode instalado

**Passo 1:** Com o Expo rodando, pressione `i` no terminal

```
Press 'a' (Android), 'i' (iOS), 'w' (web), 'c' (clear), or 'q' (quit)
i
```

**Passo 2:** O simulador iOS abrirá automaticamente

### 3.5 Recarregando a Aplicação

Após fazer alterações no seu código:

- **Recarregar automático**: Muitos IDEs fazem isso automaticamente
- **Recarregar manual**: Pressione `r` no terminal enquanto o Expo está rodando
- **Recarregar no dispositivo**: Agite o smartphone ou use o menu do Expo Go

### 3.6 Acessando o Menu do Expo

Para acessar mais opções, agite seu smartphone (dispositivo físico) ou use o menu integrado do emulador:

```
Android: ⌘+M (Mac) ou Ctrl+M (Windows/Linux)
iOS: Ctrl+⌘+Z (Mac)
```

Menu do Expo Go:
- Reload
- Go Home
- Enable/Disable Remote JS Debugging
- Show Performance Monitor
- Toggle Element Inspector

---

## 4. Conceitos Básicos do React que Existem em React Native

Se você já conhece React Web, muitos conceitos são idênticos ou muito similares. Veja os principais:

### 4.1 Componentes Funcionais e Hooks

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

### 4.2 State (Estado)

O hook `useState` funciona exatamente igual ao React Web:

```javascript
const [valor, setValor] = useState(valorInicial);
```

### 4.3 Props

Props são passadas da mesma forma:

```javascript
function Saudacao({ nome }) {
  return <Text>Olá, {nome}!</Text>;
}

// Uso:
<Saudacao nome="Maria" />
```

### 4.4 Ciclo de Vida com useEffect

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

### 4.5 Estilos

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

### 4.6 Renderização Condicional

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

### 4.7 Listas com map()

Também funciona igual:

```javascript
const itens = ['Item 1', 'Item 2', 'Item 3'];

<View>
  {itens.map((item, index) => (
    <Text key={index}>{item}</Text>
  ))}
</View>
```

### 4.8 Context API

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

### 4.9 Custom Hooks

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

### 4.10 Componentes vs Elementos

Conceitos idênticos ao React Web:

```javascript
// Componente (função)
function MeuComponente() {
  return <Text>Olá</Text>;
}

// Elemento (resultado de renderizar o componente)
const elemento = <MeuComponente />;
```

### 4.11 Principais Diferenças entre React Web e React Native

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

### 4.12 Recursos Únicos do React Native

Além dos conceitos compartilhados com React Web, React Native oferece recursos específicos para mobile:

- **AsyncStorage**: armazenamento local de dados
- **Vibration**: fazer o dispositivo vibrar
- **Camera**: acesso à câmera do dispositivo
- **Geolocation**: obter localização GPS
- **Push Notifications**: notificações push
- **Sensor APIs**: acelerômetro, giroscópio, etc.

Esses recursos geralmente requerem bibliotecas adicionais como:

```bash
npm install expo-camera expo-location expo-notifications
```

---

## Resumo

Agora você tem as ferramentas e conhecimento para começar a desenvolver com React Native e Expo! 

**Próximos passos:**

1. ✅ Instale todas as ferramentas necessárias
2. ✅ Crie seu primeiro projeto com Expo
3. ✅ Experimente modificar o `App.js`
4. ✅ Execute no seu smartphone ou emulador
5. ✅ Explore componentes nativos como `Button`, `TextInput`, `ScrollView`, `FlatList`
6. ✅ Integre navegação com React Navigation
7. ✅ Explore APIs nativas do Expo

**Recursos Úteis:**

- [Documentação Oficial Expo](https://docs.expo.dev/)
- [Documentação React Native](https://reactnative.dev/docs/getting-started)
- [Componentes React Native](https://reactnative.dev/docs/components-and-apis)
- [Expo API Reference](https://docs.expo.dev/versions/latest/)

---
