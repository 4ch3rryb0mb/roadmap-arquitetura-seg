# SSO - Single-Sign-On 

É um sistema de autenticação que permite que um usuário acesse vários sistemas ou aplicativos com somente uma única credencial de login, logo não é necessário visualizar e/ou gerir diferentes conjuntos de credenciais para cada sistema, simplificando tanto a experiência do usuário quanto a governança para nós, TI.

A experiência do usuário com o uso de um SSO pode ser simplificada abaixo:

[images/sso.png]

O SSO é cada vez mais usual tanto para empresas quanto para usuários comuns, por exemplo, temos a experiência do login através do facebook.

[images/facebook_sso.png]

Além de oferecer a conveniência de utilizar um mesmo login, é possível aumentar a complexidade de credenciais fortes e, até mesmo, ativar um MFA (Múltiplo Fator de Autenticação). Logo, além de reduzir a tendência de reutilização de senhas fracas, há uma autorização expressa do usuário (inserindo o código de acesso via SMS, E-mail, ou aplicação) que permite o acesso. 


## Quais as fragilidades do uso de um SSO? 
Partindo do pressuposto da comodidade de vincular diversas aplicações, você há um ponto único de falha de toda uma estrutura de comunicação.

1. Confiabilidade do sistema: Se o provedor de identidade (IdP) for comprometido, isso pode resultar em um acesso não autorizado a todos os sistemas e aplicativos conectados a ele. 
2. Phishing direcionado ao IdP: Ataques de phishing direcionados ao provedor de identidade podem enganar os usuários para que insiram suas credenciais em sites falsos.
3. Falta de controle de autenticação: Se um usuário já autenticado deixar seu dispositivo sem sair do SSO, outra pessoa poderá acessar os sistemas conectados.
4. Problemas de integridade do provedor de identidade: Se houver uma falha ou corrupção no provedor de identidade, isso pode interromper ou prejudicar o acesso a todos os serviços vinculados ao SSO.
5. Exposição a ataques: Se o token de autenticação gerado pelo SSO não for adequadamente protegido e configurado, ele poderá ser capturado e reutilizado por atacantes para acessar os sistemas protegidos.

Para mitigar os riscos associados à tecnologia, detalho abaixo alguns pilares essenciais.

### Robustez no provedor de identidade:
1. Utilizar autenticação multifatorial (MFA).
2. Manter o sistema do provedor atualizado com patches e atualizações de segurança.
3. Implementar políticas de senha robustas e de expiração de senhas, assim como revogação de credencial de forma automática.

### Monitoramento:
1. Implementar sistemas de monitoramento contínuo para identificação de atividades suspeitas e incomuns, como por exemplo acessos fora do horário comercial.
2. Implementar alarmes de acessos vinculado à tentativas de acessos provenientes de uma mesma origem, com atuação automática de bloqueio.

### Segregação de funções e controle de acesso
1. Limitar os privilégios de acesso com base nas funções e responsabilidades dos usuários.
2. Implementar políticas de least privilege para garantir que os usuários tenham apenas o acesso necessário para realizar suas tarefas.

### Criptografia e proteção de tokens de autenticação:
1. Use criptografia forte para proteger os tokens de autenticação durante a transmissão e armazenamento.
2. Gerenciamento de chaves para proteger os segredos de criptografia.
3. Utilize-se de JWE ou JWT para comunicação de sessões ativas, da mesma forma que limite o retorno de informações somente às necessárias para tal aplicação.

### Treinamento dos usuários:
1. O usuário é sempre o elo mais frágil e de maior impacto, logo é impressindível que eduque os usuários sobre práticas seguras de login, incluindo a importância de senhas fortes, o não compartilhamento de acessos e a identificação de tentativas de phishing.

### Auditorias e revisões regulares de segurança:
1. Realizar auditorias periódicas para identificar e corrigir possíveis fragilidades do ambiente, assim como revisar as políticas atualmente empregadas.
Testes de penetração e simulação de ataques, assim como DR (Disaster Recovery) e elaboração de um plano de incidentes. 

