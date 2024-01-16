# Configurações do SSO

Para as configurações do SSO, primeiro sugiro que segmente as necessidades, orientado a algumas questões.
- Quais tipos de pessoas vão utilizar a plataforma?
- O acesso é somente dentro de uma rede privada interna? Ou será exposto na internet?
- Haverá definição de perfis?
- A plataforma terá uma interface de login própria? Ou a ideia é aproveitar algo existente?

Agora entendendo isso, temos os protocolos associados.

##SAML
É um padrão de linguagem de marcação XML usado para trocar informações de autenticação e autorização entre partes. O SAML permite que uma entidade de autenticação (como um provedor de identidade) compartilhe informações de autenticação com uma entidade de serviço. Comumente utilizado em aplicações empresariais.

Em um fluxo básico temos o processo:
Usuário acessa o serviço que está plugado em um Service Provider;
O service provider redireciona para um Identity provider que autentica o usuário e gera um token SAML;
O token SAML possui todas as informações de nome, e-mail e dados pertinentes (nome de grupo para fazer vínculo com a aplicação);
O Identify Provider envia o token de volta ao navegador do usuário;
O navegador encaminha o token para o Service Provider;
O Service Provider verifica o token e se estiver válido, autoriza o acesso ao serviço com as devidas permissões.

Utilizando como base o autenticador Azude AD (aplicativo empresarial) para acesso ao e-mail, o Azure atua como Identify provider e o e-mail como um Service Provider. 

![Guia de início rápido para adicionar um aplicativo empresarial](https://learn.microsoft.com/pt-br/entra/identity/enterprise-apps/add-application-portal)


##OIDC
O OpenID Connect é um protocolo de identidade simples e um padrão aberto, criado utilizando o protocolo OAuth 2.0. Muito utilizado para obter informações sobre a identidade de um usuário de forma padronizada. Utilizado em sua maioria para a autenticação social de clientes na web. Utiliza-se de JSON como o formato de troca de mensagem contendo a identidade do usuáio (ID Token). 

Além do fluxo anterior explícito, o OIDC permite customização também para fluxo implícito (o Service Provider interage diretamente com o serviço de autenticação ao invés de redirecionar o usuário, sem interfirir em sua experiência). 
