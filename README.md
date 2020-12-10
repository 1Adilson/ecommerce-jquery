# jquery-project

Um desafio de criar com JS o back-end de um site e-commerce de camisetas


![O programa rodando](./img/run-python.png)
![O codigo do programa](./img/code-coin-python.png)


## Sobre
Este projeto foi um desafio de aprendizado onde tive a experiência de utilizar e aprender as ferramentas do Jquery em Javasrcipt


## O desenvolvimento 

O desenvolvimento da aplicação foi feita atraves do  <b>Visual Studio</b> utilizando Jquery.

Vou listar o passo a passo dos pontos que achei mais interessantse e importantes durante o desenvolvimento.

As regras do desafio eram:

```
// Regras adicionais para o orçamento:

// 1. Verificar se há em localStorage os parâmetros do último orçamento e se houver, carregar a página com eles.

// 2. A camisa de qualidade alta (190g/m2) deve acrescer o preço unitário em 12%.

// 3. A embalagem unitária tem um custo de 0.15 por unidade

// 4. Após cálculo do preço, há que se aplicar um desconto por quantidade, sendo: 
    // faixa 1: acima de 1.000 - Desconto de 15%
    // faixa 2: acima de 500 - Desconto de 10%
    // faixa 3: acima de 100 - Desconto de 5%
```

#### 1- Instalando Jquery
<ul>
    <li>Nesse primeiro passo aprendi sobre realizar e implementar as funcionalidades do Jquery.</li>
    <li>Aprendi a sintaxe basica do Jquery, facilitando muito o desenvolvimento</li>
    <li>O link para download do Jquery https://jquery.com/download/</li>
</ul>


#### 2- Utilizando e criando um objeto !
<ul>
    <li>Para facilitar o desenvolvimento do projeto, decidi utilizar no lugar de um banco dados 
        um objeto com as informações que seriam utilizadas </li>

```
// Objeto para pegar os preços e as fotos das camisetas

var camisetas = {
    'branca': {
        
        'gola_v': {
            'sem_estampa': {
                'preco_unit': 5.12,
                'foto': 'v-white.jpg' 
            },
            'com_estampa': {
                'preco_unit': 8.95,
                'foto': 'v-white-personalized.jpg' 
            }
        },
        
        'gola_normal': {
            'sem_estampa': {
                'preco_unit': 4.99,
                'foto': 'normal-white.jpg' 
            },
            'com_estampa': {
                'preco_unit': 8.77,
                'foto': 'normal-white-personalized.jpg' 
            }
        }
    },
    
    'colorida': {
        'gola_v': {
            'sem_estampa': {
                'preco_unit': 6.04,
                'foto': 'v-color.jpg' 
            },
            'com_estampa': {
                'preco_unit': 9.47,
                'foto': 'v-color-personalized.png' 
            }
        },
        
        'gola_normal': {
            'sem_estampa': {
                'preco_unit': 5.35,
                'foto': 'normal-color.jpg' 
            },
            'com_estampa': {
                'preco_unit': 9.28,
                'foto': 'normal-color-personalized.jpg' 
            }
        }
    }
}


// parâmetros da pesquisa

var parametros_pesquisa = {
    "quantidade": 10,
    "cor": "colorida",
    "gola": "gola_v",
    "qualidade": "q150",
    "estampa": "com_estampa",
    "embalagem": "bulk"
}
```

#### 3- Utualizando o preço
<ul>
    <li>Atualizar o preço adcionando os descontos de acordo com o pedido do cliente e outras funcionalidades estão no código abaixo</li>
</ul>

```
$(function(){

    function att_orcamento(parametros){

        var quantidade = parametros.quantidade;
        var preco_unit = camisetas[parametros.cor] [parametros.gola] [parametros.estampa].preco_unit;
        var foto = "../site_camisas/img/" + camisetas[parametros.cor] [parametros.gola] [parametros.estampa].foto;

        var valor_total = quantidade * preco_unit;
        
        if(parametros.qualidade == "q190"){

            valor_total *= 1.12;
        }

        if(parametros.embalagem == "unitaria"){

            valor_total += (quantidade * 0.15);
        }

        if(quantidade >= 1000){
            valor_total *= 0.85;
        }else if(quantidade >= 500){
            valor_total *= 0.90;
        }else if(quantidade >= 100){
            valor_total *= 0.95;
        }otacao = json.loads(req.text)
```


#### 4- Utilizando o LocalStorage
<ul>
    O LocalStorage foi importante, visando facilitar a vida do usuário.
</ul>

```
//Quantidade
    if(window.localStorage["quantidade"]){
        parametros_pesquisa.quantidade = parseInt(window.localStorage["quantidade"]);
    }

    //Cor
    if(window.localStorage["cor"]){
        parametros_pesquisa.cor = window.localStorage["cor"];
    }

    //Gola
    if(window.localStorage["gola"]){
        parametros_pesquisa.gola = window.localStorage["gola"];
    }

    //Qualidade
    if(window.localStorage["qualidade"]){
        parametros_pesquisa.qualidade = window.localStorage["qualidade"];
    }

    //Estampa
    if(window.localStorage["estampa"]){
        parametros_pesquisa.estampa = window.localStorage["estampa"];
    }

    //Embalagem
    if(window.localStorage["embalagem"]){
        parametros_pesquisa.embalagem = window.localStorage["embalagem"];   
    }

```


## Redes sociais

* [Linkedin](https://www.linkedin.com/in/adilson-júnior-5b0934187) 
* [Codepen](https://codepen.io/adilson-j-nior) 
* [GitHUb](https://github.com/1Adilson) 

## Contribuição
Todo esse projeto e aprendizado se deve a Udemy e ao professor <b>Guilherme Junqueira</b> por disponibilizar ótimos conteúdos. 

Contato da plataforma [Udemy](https://Udemy.com.br) 

## Finalização
Este projeto foi de total cunho educativo onde passei a minha visão de colocar em prática meus aprendizados em Javascrip e Jquery.
