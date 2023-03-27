Ative o BigQuery Export dos dados do Cloud Billing
Observação: Se você já teve seus dados de faturamento exportados para uma tabela do BigQuery, pode pular para a Etapa 5.

Crie seu projeto de administração de faturamento
Práticas recomendadas são para criar um projeto do Cloud que contenha todas as suas necessidades de administração de faturamento, incluindo seus dados exportados do Cloud Billing. Também é possível usar esse projeto de administração de faturamento do Cloud para itens como acesso às APIs Cloud Billing, canais do Pub/Sub para notificações programáticas de orçamento e outras tarefas de administração do Cloud Billing.

Ao usar o seletor de projetos abaixo, você cria um novo projeto de administração de faturamento. Se você já criou um, pode escolher um projeto atual. É neste projeto que você irá guardar e acessar os dados de faturamento exportados para um conjunto de dados do BigQuery.

Importante: O projeto criado ou selecionado precisa estar vinculado à mesma conta do Cloud Billing usada para os projetos do Cloud que geram os custos e preços dos dados a serem exportados e analisados.

Criar um novo projeto para garantir que você tenha as permissões necessárias ou selecione um projeto em que você tem as permissões relevantes.

Contas de faturamento
Uma conta de faturamento define quem paga pelos recursos consumidos do Google Cloud. É possível vincular um ou mais projetos a uma conta de faturamento.

Acessar a área "Faturamento"
Se você já estiver na área "Faturamento" do console do Cloud, vá para a próxima etapa deste tutorial.

Para navegar até essa área, abra o menu de navegação do console do Cloud e selecione "Faturamento".

Faturamento

Se você tiver apenas uma conta, siga para a próxima etapa.

Se tiver várias contas de faturamento
Talvez seja necessário escolher a conta de faturamento que você quer gerenciar. Para ver a conta de faturamento vinculada ao projeto selecionado, clique em Acessar a conta de faturamento vinculada. Para localizar outra conta de faturamento, clique em Gerenciar contas de faturamento e, em seguida, selecione a conta de faturamento de preferência.

Ative a exportação de dados de faturamento
Agora que você está na seção de faturamento do Console do Cloud, é hora de ativar a exportação dos seus dados de faturamento.

No menu de navegação, selecione Exportação de faturamento.

Em seguida, na seção denominada Custo de uso padrão, clique em EDITAR CONFIGURAÇÕES

Abaixo desta opção, clique no campo denominado ID do conjunto de dados. Clique na opção denominada CRIAR NOVO CONJUNTO DE DADOS e preencha o formulário que parece criar um novo Conjunto de dados para guardar todos os seus dados de faturamento.

Preencha o formulário da seguinte maneira:

Insira um código do conjunto de dados.

Insira um Local dos dados. Este local será usado para todas as tabelas deste conjunto de dados e não pode ser alterado posteriormente.

Certifique-se de que Ativar a validade da tabela NÃO esteja ativado.

Defina a opção Criptografia como Chave gerenciada pelo Google. Não use a opção Chave gerenciada pelo cliente.

Clique em Criar conjunto de dados.

Você será levado de volta à página de configurações da exportação, com seu ID do conjunto de dados devidamente pré-preenchido.

Agora, clique no botão de Salvar. Seus dados dos detalhes de custos padrão começarão a ser exportados para seu conjunto de dados do BigQuery (pode levar algumas horas para começar a ver seus dados de custo).

Observação: Será criada uma conta de serviço.
A exportação do Cloud Billing para o BigQuery usa uma conta de serviço para gerenciar as permissões do conjunto de dados.

Depois de ativar a exportação do Cloud Billing para o BigQuery, o Google adiciona automaticamente uma conta de serviço como proprietário ao conjunto de dados especificado. A conta de serviço tem esta aparência:

billing-export-bigquery@system.gserviceaccount.com

A conta de serviço é de propriedade do Google e gerenciada por ele, além de fornecer as permissões necessárias para que nosso processo off-line crie uma tabela e grave registros do Cloud Billing nela.

NÃO EXCLUA ESTA CONTA DE SERVIÇO. Isto evita que os dados sejam exportados para seu conjunto de dados do BigQuery e que os dados sejam preenchidos até que o problema seja resolvido.
