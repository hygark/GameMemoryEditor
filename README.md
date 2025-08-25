# GameMemoryEditor
## Descrição:
GameMemoryEditor.c é um programa em C projetado para manipulação de memória em jogos como Roblox e Free Fire (2024), rodando em emuladores como BlueStacks. Ele permite buscar e modificar valores na memória (ex.: saúde, moedas, munição) com uma interface de linha de comando (CLI). Usa a biblioteca windows.h para acesso à memória de processos no Windows, com logging para monitoramento. O programa é voltado para testes educacionais em ambientes privados.
Aviso Importante: Este script é para uso educacional e em ambientes privados (ex.: emuladores). Manipulação de memória em jogos pode violar os Termos de Serviço de Roblox e Free Fire, resultando em banimentos. Use com responsabilidade.

## Funcionalidades:
Busca de Valores: Escaneia a memória do processo do jogo para encontrar endereços com valores específicos (ex.: saúde = 100).
Modificação de Memória: Altera valores encontrados para novos valores (ex.: saúde para 9999).
Logging: Registra ações em arquivo (memory_editor.log) e suporta envio para webhook (ex.: Discord).
Interface CLI: Interação simples via linha de comando para especificar valores a buscar/modificar.
Limites de Segurança: Limita o número de endereços encontrados (máximo 100) e inclui tratamento de erros robusto.

## Requisitos:
Compilador C: GCC ou MSVC (ex.: MinGW para Windows, baixe em mingw-w64.org).
Sistema Operacional: Windows 10/11 (devido ao uso de windows.h).
Dependências: Biblioteca padrão do C (windows.h, incluída no Windows SDK).
Estrutura do Ambiente: Um emulador como BlueStacks rodando Roblox ou Free Fire.
Bibliotecas: Nenhuma externa necessária, mas libcurl pode ser adicionada para suporte a webhook (opcional).

## Instalação:
Crie um Repositório no GitHub (opcional para versionamento):
Vá para github.com e crie um novo repositório chamado "GameMemoryEditor".
Clone o repo para o seu PC: git clone https://github.com/hygark/GameMemoryEditor.git

Adicione o Script:
Copie o conteúdo de GameMemoryEditor.c para um arquivo C no seu diretório.

Compile o Programa:
No terminal (com MinGW instalado): gcc -o GameMemoryEditor GameMemoryEditor.c -lpsapi.

Configuração no C:
Abra o script e edite as definições no início:
PROCESS_NAME: Nome do processo do emulador (padrão: "BlueStacks.exe").
LOG_FILE: Nome do arquivo de log (padrão: "memory_editor.log").
WEBHOOK_URL: URL de um webhook Discord (crie em Discord > Server Settings > Integrations).
SCAN_INTERVAL: Intervalo entre varreduras (padrão: 100 ms).
MAX_ADDRESSES: Máximo de endereços a encontrar (padrão: 100).
VALUE_TYPE: Tipo de dado a buscar (padrão: int).



## Como Fazer Funcionar?:
Ajuste as Configurações:
Edite PROCESS_NAME para o processo do seu emulador (ex.: "BlueStacks.exe").
Compile e Execute:
Compile: gcc -o GameMemoryEditor GameMemoryEditor.c -lpsapi.
Execute: ./GameMemoryEditor.
Insira o valor a buscar (ex.: 100 para saúde) e o novo valor (ex.: 9999).


## Teste:
Abra Roblox ou Free Fire em um emulador.
O programa escaneia a memória, lista endereços encontrados e modifica os valores.
Monitore o console ou arquivo de log para resultados (ex.: "Valor modificado em 0x12345678 para 9999").

Parar o Programa:
Feche o terminal ou pressione CTRL+C.

## Exemplos de Uso:
Teste em Free Fire: Busque o valor da saúde (ex.: 100) e modifique para 9999 para teste em um servidor privado.
Teste em Roblox: Modifique moedas ou recursos em um jogo de teste (ex.: Pet Simulator, em emulador).
Logging Avançado: Configure um webhook Discord para receber notificações de varreduras e modificações.
Expansão: Adicione suporte a tipos de dados diferentes (ex.: float) ou uma GUI com Windows API.

## Aviso Legal e Ético:

Este programa é para fins educativos e testes privados. Não use em jogos públicos ou para cheating, pois pode resultar em banimentos ().
Sempre respeite os Termos de Serviço de Roblox () e Free Fire.
Para pentest ou automação ética, adapte para cenários legais.

Contribuições:
Sinta-se livre para fork o repositório no GitHub e contribuir com melhorias, como suporte a mais tipos de dados ou uma interface gráfica.
