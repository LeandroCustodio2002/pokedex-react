<div align="center">

# 🔴 Pokédex React

**Uma Pokédex inspirada no visual dos jogos, com os 1025 Pokémon,<br>estatísticas em gráfico e cálculo automático de fraquezas e resistências.**

### [▶ Abrir a Pokédex](https://leandrocustodio2002.github.io/pokedex-react/)

![React](https://img.shields.io/badge/React-19-20232A?logo=react&logoColor=61DAFB)
![styled-components](https://img.shields.io/badge/styled--components-DB7093?logo=styledcomponents&logoColor=white)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?logo=chartdotjs&logoColor=white)
![PokéAPI](https://img.shields.io/badge/PokéAPI-EF5350?logo=pokemon&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-222222?logo=githubpages&logoColor=white)

<img src="image.png" alt="Pokédex mostrando o Nidoking, com gráfico de estatísticas, tipos, fraquezas, resistências e imunidades" width="900">

</div>

---

## ✨ Funcionalidades

- 📖 **Todos os 1025 Pokémon**, de Bulbasaur a Pecharunt. A navegação dá a volta: depois do último vem o primeiro.
- 📊 **Gráfico de estatísticas** (PS, Ataque, Defesa, Ataque Especial, Defesa Especial e Velocidade) com Chart.js.
- 🛡️ **Fraquezas, resistências e imunidades** calculadas a partir dos tipos. Pokémon com dois tipos combinam os multiplicadores dos dois.
- 🎨 **Cores por tipo**: cada tipo tem o seu degradê, como nos jogos.
- 📝 **Descrição da Pokédex** vinda direto da PokéAPI.
- 🔊 **Som de interface** ao trocar de Pokémon.

## 🎨 Do protótipo ao projeto

O layout foi desenhado antes de ir para o código:

<table>
  <tr>
    <th>Protótipo</th>
    <th>Resultado</th>
  </tr>
  <tr>
    <td><img src="img/Group%206.png" alt="Protótipo da Pokédex com o Bulbasaur" width="440"></td>
    <td><img src="image.png" alt="Pokédex finalizada com o Nidoking" width="440"></td>
  </tr>
</table>

## ⚙️ Como funciona

A cada troca de Pokémon, o app faz duas chamadas à [PokéAPI](https://pokeapi.co/):

| Endpoint | O que traz |
|---|---|
| `/pokemon/{id}` | Imagem, nome, tipos e estatísticas |
| `/pokemon-species/{id}` | Descrição da Pokédex (em inglês) |

As fraquezas e resistências não vêm da API. Elas são calculadas no front com uma tabela de tipos: para cada tipo do Pokémon, o multiplicador é ×2 nas fraquezas, ×0,5 nas resistências e ×0 nas imunidades.

## 🚀 Rodando localmente

```bash
npm install
npm start
```

O app abre em [http://localhost:3000](http://localhost:3000).

Para publicar no GitHub Pages:

```bash
npm run deploy
```

## 🧩 Estrutura

```
src/
├── App.js                    # Estado do Pokémon atual, chamadas à PokéAPI e navegação
├── assets/                   # Imagens de fundo e som de interface
└── components/
    ├── containerLeft/        # Lado esquerdo: imagem e estatísticas
    ├── containerRight/       # Lado direito: navegação e informações
    ├── navBar/               # Botões Anterior / Próximo
    ├── pokemonPicture/       # Imagem e nome do Pokémon
    ├── pokemonDescription/   # Descrição, tipos, fraquezas, resistências e imunidades
    ├── statsChart/           # Gráfico de estatísticas (Chart.js)
    ├── typeMarker/           # Etiqueta colorida de cada tipo
    ├── interactionBtn/
    └── rectangle/
```

## 🛠️ Como alterar o projeto

Cada componente fica numa pasta em `src/components/`, com o `.jsx` e um `style.js` feito com [styled-components](https://styled-components.com/):

```js
// style.js
import styled from "styled-components";

export const Container = styled.div`
  /* regras de css */
`;

export const StyledBtn = styled.button`
  /* regras de css */
`;
```

```jsx
// ComponenteExemplo.jsx
import { Container, StyledBtn } from "./style";

function ComponenteExemplo() {
  return (
    <Container>
      <StyledBtn />
    </Container>
  );
}

export default ComponenteExemplo;
```

Depois, é só importar o componente no `App.js`:

```jsx
import ComponenteExemplo from "./components/componenteExemplo/ComponenteExemplo";

function App() {
  return <ComponenteExemplo />;
}
```

## 🙏 Créditos

- Dados e imagens: [PokéAPI](https://pokeapi.co/).
- Pokémon e nomes relacionados são marcas de Nintendo, Game Freak e The Pokémon Company. Projeto feito para estudo, sem fins comerciais.

---

<div align="center">

Feito por [Leandro Custódio](https://github.com/LeandroCustodio2002) · Se curtiu, deixa uma ⭐

</div>
