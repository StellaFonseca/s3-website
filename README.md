# Site estático no S3

🚀Objetivos:

* Criar um bucket S3
* Hospedar um site HTML simples (estático)
* Encerrar o bucket para não gerar gastos (exemplo realizado no free tier)

## Proposta do projeto

Esse exercício tem como objetivo demonstar conhecimentos básicos em AWS, especificamente na hospedagem de um site estático através do serviço Amazon S3.

Seu foco é na criação de um bucket no S3, configuração das permissões de acesso até sua hospedagem. Como inicialmente o objetivo é mostrar a facilidade desse serviço, aqui o exercício será realizado pelo AWS Management Console. O site em HTML simples é somente para demonstração.

## Ferramentas e requisitos

* Conta ativa na AWS
* Arquivo HTML do site
* Conhecimentos básicos sobre AWS e permissões

## Criação do Bucket

 ### Com a conta AWS configurada:

Antes de tudo é importante lembrar de escolher a região.

![Image](https://github.com/user-attachments/assets/02fb3748-e7ca-467c-8677-d78caf98771d)

 ### O nome precisa ser único globalmente.

![Image](https://github.com/user-attachments/assets/196d81fb-ac0c-4e68-bc94-e76f13a3132e)

#### Configuração Object Ownership e ACLs

Durante a criação do bucket, optei por desabilitar as ACLs, seguindo a recomendação da AWS para uma melhor gestão de segurança. A configuração escolhida foi:

Essa decisão permite que todas as permissões de acesso ao bucket e aos objetos sejam controladas exclusivamente através de Bucket Policies, centralizando a gestão de segurança e evitando erros relacionados a permissões individuais em objetos.

 ### Block Public Access settings

![Image](https://github.com/user-attachments/assets/116380e1-ebb4-4f72-97dd-9efbb5f64011)

 Para que o site fosse acessado publicamente na internet, foi necessário desativar o bloqueio total de acesso público, já que por padrão a AWS bloqueia todo acesso, porém o obejtivo do exercício é justamente hospedar um site público (essa ação foi feita seguindo a documentação oficial da AWS).
 Para garantir a segurança, só o arquivo do site foi exposto.

 ### Bucket criado

 ![Image](https://github.com/user-attachments/assets/f4686ac3-bc0d-4818-89ff-8c932814fe66)

 * Em propriedades

 ### Static Website Hosting

 ![Image](https://github.com/user-attachments/assets/dd44899a-2d24-4287-8d10-a3480dc7e5aa)

 Essa configuração permite que o site seja acessado publicamente.

 * Em "objetct" foi feito o upload da pasta com os arquivos do site.

 ![Image](https://github.com/user-attachments/assets/a4f0f5f5-c082-41c1-b110-a266f8f840da)

 * Opção marcada permitindo que os arquivos pudessem ser vistos publicamente pelo navegador.

 A AWS exibe um alerta dizendo que não é recomendado liberar leitura pública, para evitar erros de segurança, mas no caso de sites estáticos, esse passo é esperado e documentado pela própria AWS.
 
No futuro, para projetos com mais controle de segurança, o ideal é realizar esse tipo de liberação apenas via Bucket Policy, evitando o uso de ACLs individuais.

### 🎯Site Hospedado

Com a Object URL acessada o site já aparece.

![Image](https://github.com/user-attachments/assets/67fdc446-af30-49c8-95c7-4aae7e29d456)

### ❗Excluindo para não gerar gastos

Como o exercício foi feito e o objetivo é somente a hospedagem e demonstração, como usei o free tier, é importante excluir os objetos e o bucket para evitar possíveis gastos.

![Image](https://github.com/user-attachments/assets/3698c10b-d3f1-4b17-8183-249d1b8b4ee1)

![Image](https://github.com/user-attachments/assets/f49d6eac-c256-4607-bcc5-d202600b5e78)

### Considerações finais

Por ser de nível básico, é um exercício rápido de fazer, mas também é importante para se adaptar as diferentes permissões e modos de ser feito.
