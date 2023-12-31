# Azure Update Manager
O Gerenciador de Atualizações do Azure é um serviço unificado para ajudar a gerenciar e controlar as atualizações de todos os seus computadores. Você pode monitorar a conformidade de atualização do Windows e do Linux em suas implantações no Azure, no local e em outras plataformas de nuvem em um único painel. Além disso, você pode usar o Gerenciador de Atualizações para fazer atualizações em tempo real ou agendá-las em uma janela de manutenção definida.

Abaixo listei alguns pontos importantes de se levar em conta, todas os pontos foram tirados da documentação oficial e de experiência com a ferramenta.

Fonte: https://learn.microsoft.com/pt-br/azure/update-center/overview?tabs=azure-vms

## 1 - Automatic Onboaring
- Ao se criar um novo servidor ele será exibido no painel do Update Manager;
- Ao mandar qualquer comando para o servidor a central instala uma extensão/Agente na VM para gerenciar os updates e reports;
	
## 2 - Assessment
- Periodic assessment Pode ser automatizado, recomendação 24 Horas;
- Assessment reporta estado do servidor com realação aos updates;
- Verifica novas atualizações;
	
## 3 - One time update
- Instala update pontualmente nas VMS selecionadas;
- Update precisa estar disponível;
- Possivel filtrar Update a ser instalado;

## 4 - Scheduled Patching
- Configura datas de patching/reboot e condição do reboot;
- Dynamic Scoping (Preview) - Possível criar filtors dinâmicos baseados em Subscription, Resource Group, Location, Resource Type, OS Type e TAGS;

## 5 - Hotpatching 
- Somente para Windows Server 2022 - Instala updates sem pedir reboot
- Somente updates de segurança;
- Ainda necessário dar reboot para patchs que não estao incluídos no hotpatching;

## 6 - Virtual Machine
- Ao criar uma VM, idealmente, configurar a opçãode update na guia management como "Manual";

## 7 - Azure Resource Graph
- Possivel criar queries para gerar dashboards personalizadas;

## 8 - Comunicação com a internet
- VMs precisam ter liberação para falar com o Windows Update;
  - *.download.windowsupdate.com
  - *.dl.delivery.mp.microsoft.com
  - *.delivery.mp.microsoft.com
  - *.prod.do.dsp.mp.microsoft.com
  - emdl.ws.microsoft.com
  - *.dl.delivery.mp.microsoft.com
  - *.windowsupdate.com
  - *.delivery.mp.microsoft.com
  - *.update.microsoft.com
  - tsfe.trafficshaping.dsp.mp.microsoft.com
  - Port 1688
