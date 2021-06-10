# Blog do código
> Uma API de blog em Node.js

# Política de Acesso  ao Conteúdo

# Propósito

Esse documento contém todas as informações necessárias sobre controle de acesso ao conteúdo do Blog do Código.

Esse documento deve ser lido por todas as pessoas que trabalham no Blog do Código.

# Autenticação

Antes de prosseguir com o uso da API, é necessário que crie uma nova conta através da rota POST /usuario, e em seguida, verificar o email da nova conta através da rota POST/usuario/verifica_email/:token.

Com a conta criada e verificada, use a rota de login POST /usuario/login para obter um token de acesso através do cabeçalho Authorization na resposta. Use esse cabeçalho nas demais requisições para se autenticar com a API e prosseguir com controle de acesso ao conteúdo.

# Controle de conteúdo do Blog 

No nosso blog, temos o cargo de assinante. A pessoa com cargo de assinante apenas pode ler os posts do blog, os posts de qualquer pessoa.

Além do cargo de assinante, também temos o cargo de editor. A pessoa com cargo de editor pode e deve cadastrar novos posts no blog e gerenciá-los.

Por último, o blog possui o cargo de admin. O cargo de administrador é para as pessoas que vão gerenciar os usuários e posts do nosso blog.

# Teste de custo para gerar hash de senha
const bcrypt = require('bcrypt');    
for (let custo = 6; custo < 18; custo++) {
  const tempoInicial  = Date.now();
  bcrypt.hash('A', custo).then(
    () => console.log(`custo: ${custo}; tempo: ${ Date.now() - tempoInicial} ms`)
  );
} 
# Comando para gerar uma senha segura ramdomica
node -e "console.log( require('crypto').randomBytes(256).toString('base64')) "

#redis
O Redis não suporta oficialmente o sistema operacional Windows, mas é possível instalar uma versão experimental, mantida pelo grupo Microsoft Open Tech. Por se tratar de uma versão experimental, é importante deixar claro que até o momento em que este curso foi escrito a sua instalação é recomendada apenas em ambiente de desenvolvimento.

Outra observação a ser feita é que atualmente apenas a versão para instalações do Windows de 64-bit é suportada oficialmente pelo projeto Microsoft Open Tech.

A versão mantida pelo Microsoft Open Tech pode ser obtida através do link https://github.com/MSOpenTech/redis mas, para simplificar, vamos realizar o download de um arquivo de instalação no repositório do projeto através do link:

https://github.com/MSOpenTech/redis/releases/download/win-3.0.500/Redis-x64-3.0.500.msi

# se a instalação do redis não funcionar 
Ir no site https://github.com/dmajkic/redis/downloads, peguar a ultima versão zipada, descompactar. Execurar o redis-server e em seguida o redis-cli. Para cada uma irá abrir uma instância do prompt de comando. Deixar aberta até finalizar os testes.

# para saber mais sobre técnicas de controle de acesso
Durante o curso, trabalhamos com duas técnicas de controle de acesso: o PABC (controle de acesso baseado em permissões) e o RBAC (controle de acesso baseado em cargos/títulos).

Essas duas técnicas funcionam perfeitamente para o nosso blog e atendem nossa necessidade, mas possuem algumas contra-indicações de uso ou limitações, como por exemplo, RBAC não nos ajuda a fazer controle de acesso baseado em conteúdo. É importante conhecer outras técnicas para controle de acesso, inclusive, como usá-las em conjunto.

Caso se interesse para saber mais, indicamos essa página da OWASP, em inglês: https://cheatsheetseries.owasp.org/cheatsheets/Access_Control_Cheat_Sheet.html#introductio

# Para saber mais: JSDoc e mais tags

Usamos algumas tags para documentar partes da nossa classe, mas existem dezenas de tags e marcações que podem ser utilizadas para nos ajudar a documentar o nosso código. Você pode encontrar essas tags e marcações na documentação do esdoc: https://esdoc.org/manual/tags.html

Além do esdoc, você também pode conhecer o JSDoc, projeto que serviu de inspiração para o esdoc: https://jsdoc.app/