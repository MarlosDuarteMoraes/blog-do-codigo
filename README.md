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
