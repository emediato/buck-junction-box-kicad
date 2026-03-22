## debug checklist schematic

https://resources.pcb.cadence.com/blog/2024-electrical-schematic-design-checklist


### servia axis hunting
“Servo axis is hunting around its setpoint. Chassis ground and signal ground.”

A oscilação (“hunting”) ao redor do setpoint normalmente indica ruído elétrico, problemas de referência de terra, ganhos mal ajustados ou instabilidade no loop de controle.
Como você mencionou terra de chassi e terra de sinal, a prioridade é verificar se há diferença de potencial ou acoplamento de ruído entre esses dois referenciais.


1. Verifique integridade de aterramento (principal suspeito)
Passo 1 — Meça a diferença entre Signal GND e Chassis GND.  Isso indica corrente parasita ou acoplamento de ruído correndo entre os dois terras. Porque ruído entre terras é um dos maiores causadores de hunting em servo loops

Use um multímetro no modo AC e depois DC.
Diferencial > 20–50 mV já pode causar ruído em drives sensíveis.
Se houver diferença → problema de aterramento é provável.
 o terra de sinal deve ser um ponto de referência estável e livre de ruído. Já o terra de chassi recebe correntes de blindagem, interferência eletromagnética (EMI) e retornos de potência — ou seja, é um terra “sujo”.
Se houver diferença de potencial entre esses dois terras, mesmo pequena, essa diferença entra diretamente como ruído no sinal analógico ou digital de controle, causando:
oscilação no setpoint (hunting);
jitter no comando do servo;
leituras instáveis do encoder;
instabilidade geral do loop de controle.


2. Desacople terras para teste
(Objetivo: descobrir se o ruído vem do chassis)
Teste A — Isolar temporariamente o GND de sinal do GND de chassis
Verifique se o drive permite separação física de ambos.
Se ao separar o ruído reduz → interferência está entrando pelo terra do chassis.
Teste B — Reconectar com único ponto de referência
Aterramento tipo “estrela” em um ponto só.
Evitar múltiplos caminhos de retorno.

3. Inspecione cabos, blindagens e roteamento
Servo hunting pode vir de ruído em encoders ou em cabos de comando.

Garanta que o shield dos cabos:
está conectado apenas em um lado (normalmente no drive/chassis),
não está conectado no motor e drive simultaneamente (evita loops de terra).
Separe fisicamente:
cabos de potência,
cabos de encoder,
cabos de sinal analógico.


 4. Verifique potenciais fontes de ruído
Faça testes desligando temporariamente:

inversores próximos,
fontes chaveadas,
motores de alta corrente no mesmo painel.

Se o hunting parar → ruído eletromagnético externo.

 5. Avalie parâmetros de controle (caso o problema não seja terra)

Ganho proporcional (P) muito alto → hunting.
Falta de filtro de entrada no comando analógico → jitter.
Loop do encoder com ruído → posição instável.

Teste:
reduzir P em 10–20%,
aumentar suavização (filtro) se existir.

 6. Teste final: comando em malha aberta

Desconecte temporariamente o sinal de referência (setpoint).
Coloque o drive em modo jog ou torque only (se permitido).
Se o motor ficar estável:
a origem da oscilação está no sinal de comando ou no aterramento.
Se continuar instável:
problema interno no drive, encoder ou parâmetros.

O hunting provavelmente está relacionado a mau aterramento entre “chassis ground” e “signal ground”.
Isolamento se faz verificando diferencial, separando terras, eliminando loops de shield e reorganizando retorno de sinal.


Circuito de alta impedância de entrada
Um circuito high‑Z praticamente não consome corrente do sinal de entrada.
Mínimo carregamento da fonte (sensor ou estágio anterior)
1. Não carrega o sensor (baixa interação com a fonte do sinal)
1. Maior suscetibilidade a ruído


   
## books

1. The Art of Electronics – Paul Horowitz & Winfield Hill
2. Troubleshooting Analog Circuits – Robert A. Pease
3. Electronic Troubleshooting and Repair Handbook – Homer L. Davidson
4. Practical Electronics for Inventors – Paul Scherz & Simon Monk
5. Practical Troubleshooting of Electronic Circuits for Engineers and Technicians – IDC Technologies
6. Electronic Device and Circuit Theory – Robert Boylestad & Louis Nashelsky
7. Power Supply Cookbook – Marty Brown
