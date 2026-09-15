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

1. Fork esse repositório: [infoweb-pos/rn-01-introducao](https://github.com/infoweb-pos/rn-01-introducao)
2. No seu repositório, clique no botão verde **"Code"**
3. Clique na aba **"Codespaces"**
4. Clique em **"Create codespace on main"**

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

### 2.2 Verificando o Git

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

No terminal do Codespace, crie um novo projeto Expo:

```bash
npx create-expo-app@latest
```

### 3.2 Respondendo às Perguntas do npx e do expo

O npx e expo fará algumas perguntas:

```
Need to install the following packages:
create-expo-app@4.0.0
Ok to proceed? (y)
```
**Responda `y`**: digite `y` e `Enter` para continuar o processo de criação do aplicativo react native com expo

```
? What is your app named? › my-app
```

**Responda: `my-app`** pressione `Enter` que permanecerá o nome padrão do aplicativo

```
? Select an Expo SDK version: › - Use arrow-keys. Return to submit.
❯   Latest (SDK 57) - Recommended for most projects
    Other SDK version…
```

**Responda: `Latest (SDK 57)`** pressione `Enter`

```
? You are creating a project inside of an existing Git repository. Skip initializing a new git repository? › (Y/n)

```

**Responda `y`**: digite `y` para continuar o processo de criação do aplicativo react native com expo

**O resultado** deve parecer com algo abaixo:

```bash
✔ What is your app named? … my-app
✔ Select an Expo SDK version: › Latest (SDK 57)
Creating my-app using the default template.

Tip:
  • npx create-expo-app --template  to pick from other templates
  • npx create-expo-app --example   to explore https://github.com/expo/examples

✔ Downloaded and extracted project files.
> npm install
npm warn deprecated uuid@7.0.3: uuid@10 and below is no longer supported.  For ESM codebases, update to uuid@latest.  For CommonJS codebases, use uuid@11 (but be aware this version will likely be deprecated in 2028).

added 607 packages, and audited 608 packages in 2m

48 packages are looking for funding
  run `npm fund` for details

14 moderate severity vulnerabilities

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.

✅ Your project is ready!

To run your project, navigate to the directory and run one of the following npm commands.

- cd my-app
- npm run android
- npm run ios # you need to use macOS to build the iOS project - use the Expo app if you need to do iOS development without a Mac
- npm run web
✔ You are creating a project inside of an existing Git repository. Skip initializing a new git repository? … yes
```

### 3.3 Entrando na Pasta do Projeto

```bash
cd my-app
```

### 3.4 Estrutura do Projeto Criado

Veja a estrutura no Codespace clicando na pasta do projeto no Explorer:

```
my-app/
├── .claude/
├── .expo/                # Arquivos temporários do Expo/Metro
├── .gitignore            # Arquivos ignorados pelo Git
├── .vscode/              # Configurações do editor/VS Code
├── assets/
│   └── images/
│       └── tabIcons/
├── node_modules/         # Dependências do projeto
├── scripts/
│   └── reset-project.js
├── src/
│   ├── app/
│   │   ├── _layout.tsx
│   │   ├── explore.tsx
│   │   └── index.tsx
│   ├── components/
│   │   ├── animated-icon.module.css
│   │   ├── animated-icon.tsx
│   │   ├── animated-icon.web.tsx
│   │   ├── app-tabs.tsx
│   │   ├── app-tabs.web.tsx
│   │   ├── external-link.tsx
│   │   ├── hint-row.tsx
│   │   ├── themed-text.tsx
│   │   ├── themed-view.tsx
│   │   ├── web-badge.tsx
│   │   └── ui/
│   │       └── collapsible.tsx
│   ├── constants/
│   │   └── theme.ts
│   ├── global.css
│   ├── hooks/
│   │   ├── use-color-scheme.ts
│   │   ├── use-color-scheme.web.ts
│   │   └── use-theme.ts
├── AGENTS.md
├── app.json              # Configuração do app Expo
├── CLAUDE.md
├── expo-env.d.ts
├── LICENSE
├── package.json          # Scripts e dependências do projeto
├── package-lock.json     # Versões exatas das dependências
├── README.md             # Documentação do projeto
├── tsconfig.json
└── .gitignore            # Arquivos ignorados pelo Git
```

## 4. Como Executar o Aplicativo no Codespace

### 4.1 Iniciando o Servidor Expo

No terminal do Codespace (dentro da pasta do projeto), execute:
Crie uma conta em [expo.dev](https://expo.dev/)

```bash
npx expo login

```

Você verá uma saída parecida a:
```bash
Log in to EAS with email or username (exit and run 'npx expo login --help' for other login options)
✔ Email or username … leonardo.minora@gmail.com
✔ Password … ********************

```

Agora inicie o expo com o comando `npx expo start --tunnel`

Você verá uma saída similar a:

```
Starting project at /workspaces/rn-01-introducao/my-app
Using src/app as the root directory for Expo Router.
React Compiler enabled
 ERROR  An unknown error occurred while installing React Native DevTools. Details:

/workspaces/rn-01-introducao/my-app/node_modules/@react-native/debugger-shell/bin/react-native-devtools: error while loading shared libraries: libatk-1.0.so.0: cannot open shared object file: No such file or directory

Starting Metro Bundler

Tunnel connected.
Tunnel ready.
▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄
█ ▄▄▄▄▄ █▀ █▀▀▄▄▀ ▄▄▄▀█ ▄▄▄▄▄ █
█ █   █ █▀ ▄ █▀▀ ▄▀█ ▄█ █   █ █
█ █▄▄▄█ █▀█ █▄█▄▀▄▄▄▄▄█ █▄▄▄█ █
█▄▄▄▄▄▄▄█▄█▄█ █▄█ █▄█ █▄▄▄▄▄▄▄█
█ ▄▄ ▄█▄ ▄ ▄█▄ ███ ▀▀▀▄▀▄▀▄▀▄▀█
█▄▀▄▀ ▄▄▀▀ ▀ ▄▄▄ ▄█▄▀█▀█▄▄█▄ ██
███▀▄▄▀▄▄▀▄▀▄▀▄▄▄▄ ▀▀  ▀▀▀▀ ▄▀█
█▄▀▀▄▀ ▄███▀█▀█▄ █▄▀█▄█▄▀ ▄▄▀██
█▀ ████▄▀▄ ▄█▄ ▄█▄ ▀▀▀▀▀ ▀▀ ▄ █
█ █ ▄ ▀▄▀▀█▀ ▄█▀ █▄█▀▀▀▄██ ▄███
█▄█▄▄▄▄▄▄▀▀▄▄ ▄ ▄▄▄█▄ ▄▄▄  ▄▀▀█
█ ▄▄▄▄▄ █▄▀▄█▄▄█ █▄   █▄█ ▀████
█ █   █ █ █▄▀█▄▄█▄▄▀▀ ▄▄▄▄▀ ▀ █
█ █▄▄▄█ █ ▄▀▀▀█   █▄▄ ▄▄ ▄▀▄ ██
█▄▄▄▄▄▄▄█▄███▄▄▄██▄▄▄██████▄███

› Scan the QR code above to open in Expo Go.
› Metro: exp://tnkjti4-leonardo-minora-8081.exp.direct
› Web: http://localhost:8081

› Using Expo Go (Press s to switch to development build)
› Press ? │ show all commands

Logs for your project will appear below. Press Ctrl+C to exit.

```

Com o expo iniciado, agora precisa tornar a porta pública do codespace.
Ao lado da aba do `Terminal` no codespace, tem a aba `Portas`.
Clique nesta aba para aparecer as portas abertas do seu codespace.
Deve ter 2 portas abertas, ambas com visibilidade `Private`.
Na porta 8081, clique com o botão direito para aparecer um menu de contexto.
Nesse menu, clique em `Visibilidade da porta` e selecione `Public`.

### 4.2 Testando o aplicativo

Você pode testar o aplicativo no próprio navegador ou no seu celular.
Se quiser testar no navegador:

**Passo único** Ainda em portas no codespace, clique no símbolo de navegador (um círculo com hashtag dentro) na porta 8081

Se quiser testar no seu smartphone:

**Passo 1:** Instale o app Expo Go
- Android: [Play Store - Expo Go](https://play.google.com/store/apps/details?id=host.exp.exponent)
- iOS: [App Store - Expo Go](https://apps.apple.com/us/app/expo-go/id982107779)

**Passo 2:** Abra o aplicativo no celular
- com o aplicativo da câmera, aponte para o qrcode do terminal no codespace
- o Expo Go será aberto e o aplicativo será carregado


### 4.3 Testando Mudanças no Código (Hot Reload)

Com o app rodando no navegador:

1. Abra o arquivo `src/app/index.tsx` no Codespace
2. Mude o texto de qualquer componente `<ThemedText>`
3. O codesapce **automaticamente** salva o arquivo (`Ctrl + S`)
4. **Automaticamente** a mudança aparecerá no navegador sem recarregar

**Exemplo:**

Mude de:
```tsx
<ThemedText>Welcome to&nbsp;Expo</ThemedText>
```

Para:
```tsx
<ThemedText>React Native é incrível! 💻📱</ThemedText>
```

Veja a mudança aparecer no simulador!

### 4.5 Parando o Servidor

Para parar o servidor Expo, pressione `Ctrl + C` no terminal.

### 4.6 Atalhos Úteis do Terminal Expo

Enquanto o servidor está rodando:

| Tecla | Ação |
|-------|------|
| `w` | Abrir no navegador          |
| `a` | Abrir em emulador Android   |
| `i` | Abrir em emulador iOS       |
| `r` | Recarregar app              |
| `m` | Mostrar menu de mais opções |
| `c` | Limpar terminal             |
| `q` | Parar servidor              |

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
