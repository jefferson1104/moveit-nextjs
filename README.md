Fazer documentacao no github e subir o app no repositorio
- como executar o app em maquina local
- quais funcionalidades existe no app
- fazer um gif do app
- prints do app

Ajustar a responsividade do app
Trocar cores do app, criar um tema dark
Fazer um pwa do app

Criar um login via github utilizando oauth 
  - https://www.youtube.com/watch?v=Cz55Jmhfw84&ab_channel=Rocketseat
  - pesquisar oauth github como fazer no nextjs
  - projeto no figma 
  - criar sidebar
  - criar tela de compartilhar no twitter com thumbnail
  - criar tela de ranking

Link layout do projeto melhorado no figma 
https://www.figma.com/file/vRbW1u0CEZuG2zE6bU5qLg/Move.it-2.0/duplicate  

### INICIANDO PROJETO
```bash
# Inicie um projeto nextjs com yarn
$ yarn create next-app nomeDoProjeto

# Instale as dependencias de desenvolvimento necessarias para trabalhar com Typescript no seu projeto
$ yarn add typescript @types/react @types/react-dom @types/node -D

# Instalando a biblioteca de js-cookie
$ yarn add js-cookie

# Instalando a dependencia de desenvolvimento para tipagens do js-cookie
$ yarn add @types/js-cookie -D

``` 

### O QUE É NEXTJS ?
O nextjs é um framework da biblioteca reactjs, este framewok nos trás de forma pronta, um conjunto de funcionalidades 
que repetimos em todas os projetos com reactjs. Trazendo esse conjunto de funcionalidades, conseguimos de uma forma 
simples utiliza-los, um exemplo claro é o nosso roteamento de paginas, nao precisando instalar bibliotecas externas para 
ter este recurso.

O Foco principal do nextJS foi resolver o problema de indexação pelos motores de buscas como o google, bing, yandex, e 
ate mesmo aqueles crawlers das redes sociais, este foi o maior objetivo do nextJS fazer com que o SEO das aplicações 
construidas com nextjs tenham melhores desempenhos nesse quesito, entre outras muitas funcionalidades, o nextjs tambem 
trabalha melhor com Single-Page-Application (SPA) Server-Side-Rendering (SSR) seu principal diferencial e tambem com 
Static-Site-Generation (SSG).
<br><br>

#### O QUE É SPA ? (Single Page Application)
O single page application traduzindo é uma aplicação de unica pagina, todo seu conteudo é construido a partir do 
frontend por isso nao é tao recomendado para blogs, e-commerces ou qualquer outro projeto publico que necessite de SEO, 
pois seu conteudo não é renderizado pelo servidor, para esta necessidade utilizamos o SSR.

Como toda a interface de uma SPA é construida no frontend ganhamos performance quando nao precisamos recarregar 
determinado componente, pois ele carrega uma unica vez e só é alterado o conteudo de uma determinada rota.

Por exemplo: quando estamos em uma aplicação que a sidebar é renderizada em todas as rotas, nao precisamos recarregar 
toda vez que estivermos navegand, apenas mudamos o conteudo da rota.
<br><br>

#### O QUE É SSR ? (Server Side Rendering)
A grande solução para o SEO (Search Engine Optimization), utilizando o SSR conseguimos fazer com que a interface da 
nossa aplicação seja interpretada e construida pelo backend (servidor com NodeJS). 

Dessa maneira as informações carregadas pelo banco de dados e sua api é renderizada na interface web antes que o usuario 
acesse completamente a pagina, isso tambem funciona com os motores de buscas, e faz com que todo o conteudo seja indexado.
<br><br>

#### O QUE É SSG ? (Static Site Generation)
Com o nextjs conseguimos criar uma pagina estatica com seu conteudo, e determinar um valor de tempo para que este 
conteudo seja atualizado sempre que for necessario ou que tenha alguma alteração, evitando que o servidor tenha menos 
requisicoes toda vez que um usuario acessar aquela pagina, se ela nao mudar nao existe a necessidade de fazer uma nova
requisicao na api para trazer o seu conteudo.

Exemplo: imagine um blog grande com muitos usuarios e que a cada 10 minutos sua pagina principal tenha novas noticias, 
imagine que dentro a cada 5 minutos 1 milhão de usuarios acessem esse blog, iria ficar muito pesado o servidor receber 
1 milhao de requisicoes a cada 5 minutos. 

Entao utilizando o nextJS e o recurso de Static Site Generation podemos criar um html, css e javascript estatico para
essa pagina sempre que seu conteudo for atualizado, evitando assim essas requicões na api para trazer novos conteudos.
<br><br>


#### CONTEXT API
O context api sao formas de conseguir compartilhar informacoes entre componentes dentro de uma aplicacao.

exemplo de uma estrutura basica de um contexto:
```javascript
import { createContext, ReactNode } from 'react';

interface CountdownContextData {

}

interface CountdownProviderProps {
  children: ReactNode;
}


const CountdownContext = createContext({} as CountdownContextData);

export function CountdownProvider({ children }: CountdownProviderProps) {

  

  return (
    <CountdownContext.Provider value={{}}>
      { children }
    </CountdownContext.Provider>
  )
}
```

## LOCAL STORAGE, SESSION STORAGE e COOKIES
Local storage e um meio que guarda dados do tipo chave/valor, os dados sempre sao armazenados como textos, e os dados se
mantem mesmo quando fechamos o navegador e abrimos ele novamente, enquanto o usuario nao limpar o browser aquele dado
continua.

Session storage, faz a mesma coisa que o local storage com uma unica diferenca de que, os dados continuam armazenandos 
enquanto houver aquela sessao, ou seja, se voce fechar o navegador ou reiniciar seu computador aqueles dados sao nao
continuam salvos.

Os cookies e a maneira mais antiga de salvar dados no navegador, ele tambem tem suas funcionalidades muito semelhante 
ao local storage, porem tem seus diferenciais como por exemplo salvar os dados em mais de um dominio, colocar um tempo 
para os dados salvos expirar, definir se o acesso as esses dados sao apenas pelo backend ou frontend entre diversas 
outras funcionalidades.