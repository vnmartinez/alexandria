---
area: engenharias
curso: engenharia-de-software
nivel: introdutorio-a-avancado
atualizado: 2026-10-28
---

↑ [[areas/engenharias|Engenharias e Tecnologia]]

# Engenharia de Software

Percurso autodidata para quem quer a formação de um bacharel em Engenharia de Software:
do ciclo básico de matemática e programação até requisitos, arquitetura, testes, processos,
gestão e operação de software. Serve a quem começa do zero, a quem já programa e quer
fundamentos, e a quem estuda para concursos ou pós-graduação na área.

> Este percurso não equivale a uma graduação, não inclui estágio nem trabalho de conclusão supervisionado e não confere diploma.

## Como usar

Estude os módulos na ordem numérica. Comece um módulo só depois de concluir todos os que
aparecem em "Depende de": a numeração já respeita essas dependências, então seguir a ordem
nunca deixa um pré-requisito para trás. Não há prazo: avance no seu ritmo.

O mapa abaixo mostra, para cada módulo, de quais outros ele depende. Os módulos 1 a 4 não
dependem de nada e formam o ponto de partida. Se você já domina um módulo, confira o
"Resultado esperado" dele; se consegue cumpri-lo, marque os tópicos e siga adiante.
Os Módulos 1, 4 e 6 (Cálculo I, Álgebra Linear e Física I) vêm do núcleo comum de
engenharia e aparecem como obrigatórios em menos universidades (veja Fontes); o Módulo 6
não é pré-requisito de nenhum outro.

Em cada módulo, leia uma obra básica inteira nos temas dos tópicos; use as complementares
para aprofundar e a alternativa aberta quando não tiver acesso às pagas. Marque os tópicos
concluídos com `[x]`.

## Mapa de dependências

| Módulo | Depende de |
|---|---|
| 1. Cálculo I | — |
| 2. Matemática Discreta e Lógica | — |
| 3. Algoritmos e Programação | — |
| 4. Álgebra Linear | — |
| 5. Probabilidade e Estatística | 1, 2 |
| 6. Física I | 1 |
| 7. Programação Orientada a Objetos | 3 |
| 8. Estruturas de Dados | 2, 3 |
| 9. Introdução à Engenharia de Software | 3 |
| 10. Arquitetura e Organização de Computadores | 2, 3 |
| 11. Projeto e Análise de Algoritmos | 2, 8 |
| 12. Paradigmas de Programação | 7 |
| 13. Banco de Dados | 2, 3 |
| 14. Sistemas Operacionais | 10 |
| 15. Redes de Computadores | 14 |
| 16. Processos de Software e Métodos Ágeis | 9 |
| 17. Engenharia de Requisitos | 16 |
| 18. Análise e Projeto Orientados a Objetos | 7, 17 |
| 19. Projeto de Software e Padrões de Projeto | 18 |
| 20. Interação Humano-Computador | 17 |
| 21. Teste de Software | 7, 9 |
| 22. Arquitetura de Software | 19 |
| 23. Gerência de Configuração e DevOps | 21 |
| 24. Qualidade e Medição de Software | 5, 16, 21 |
| 25. Manutenção e Evolução de Software | 19, 23 |
| 26. Desenvolvimento Web | 13, 15, 19, 20 |
| 27. Desenvolvimento para Dispositivos Móveis | 26 |
| 28. Sistemas Distribuídos | 15, 22 |
| 29. Gerência de Projetos de Software | 16 |
| 30. Engenharia de Software Experimental | 5, 16 |
| 31. Inteligência Artificial | 4, 5, 11 |
| 32. Computação, Ética e Sociedade | 9 |
| 33. Empreendedorismo e Inovação | 29 |

## Índice

1. [[#Módulo 1 — Cálculo I|Módulo 1 — Cálculo I]]
2. [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2 — Matemática Discreta e Lógica]]
3. [[#Módulo 3 — Algoritmos e Programação|Módulo 3 — Algoritmos e Programação]]
4. [[#Módulo 4 — Álgebra Linear|Módulo 4 — Álgebra Linear]]
5. [[#Módulo 5 — Probabilidade e Estatística|Módulo 5 — Probabilidade e Estatística]]
6. [[#Módulo 6 — Física I|Módulo 6 — Física I]]
7. [[#Módulo 7 — Programação Orientada a Objetos|Módulo 7 — Programação Orientada a Objetos]]
8. [[#Módulo 8 — Estruturas de Dados|Módulo 8 — Estruturas de Dados]]
9. [[#Módulo 9 — Introdução à Engenharia de Software|Módulo 9 — Introdução à Engenharia de Software]]
10. [[#Módulo 10 — Arquitetura e Organização de Computadores|Módulo 10 — Arquitetura e Organização de Computadores]]
11. [[#Módulo 11 — Projeto e Análise de Algoritmos|Módulo 11 — Projeto e Análise de Algoritmos]]
12. [[#Módulo 12 — Paradigmas de Programação|Módulo 12 — Paradigmas de Programação]]
13. [[#Módulo 13 — Banco de Dados|Módulo 13 — Banco de Dados]]
14. [[#Módulo 14 — Sistemas Operacionais|Módulo 14 — Sistemas Operacionais]]
15. [[#Módulo 15 — Redes de Computadores|Módulo 15 — Redes de Computadores]]
16. [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16 — Processos de Software e Métodos Ágeis]]
17. [[#Módulo 17 — Engenharia de Requisitos|Módulo 17 — Engenharia de Requisitos]]
18. [[#Módulo 18 — Análise e Projeto Orientados a Objetos|Módulo 18 — Análise e Projeto Orientados a Objetos]]
19. [[#Módulo 19 — Projeto de Software e Padrões de Projeto|Módulo 19 — Projeto de Software e Padrões de Projeto]]
20. [[#Módulo 20 — Interação Humano-Computador|Módulo 20 — Interação Humano-Computador]]
21. [[#Módulo 21 — Teste de Software|Módulo 21 — Teste de Software]]
22. [[#Módulo 22 — Arquitetura de Software|Módulo 22 — Arquitetura de Software]]
23. [[#Módulo 23 — Gerência de Configuração e DevOps|Módulo 23 — Gerência de Configuração e DevOps]]
24. [[#Módulo 24 — Qualidade e Medição de Software|Módulo 24 — Qualidade e Medição de Software]]
25. [[#Módulo 25 — Manutenção e Evolução de Software|Módulo 25 — Manutenção e Evolução de Software]]
26. [[#Módulo 26 — Desenvolvimento Web|Módulo 26 — Desenvolvimento Web]]
27. [[#Módulo 27 — Desenvolvimento para Dispositivos Móveis|Módulo 27 — Desenvolvimento para Dispositivos Móveis]]
28. [[#Módulo 28 — Sistemas Distribuídos|Módulo 28 — Sistemas Distribuídos]]
29. [[#Módulo 29 — Gerência de Projetos de Software|Módulo 29 — Gerência de Projetos de Software]]
30. [[#Módulo 30 — Engenharia de Software Experimental|Módulo 30 — Engenharia de Software Experimental]]
31. [[#Módulo 31 — Inteligência Artificial|Módulo 31 — Inteligência Artificial]]
32. [[#Módulo 32 — Computação, Ética e Sociedade|Módulo 32 — Computação, Ética e Sociedade]]
33. [[#Módulo 33 — Empreendedorismo e Inovação|Módulo 33 — Empreendedorismo e Inovação]]

## Bibliografia

Obras citadas nos módulos, em ordem de primeira aparição. Metadados, licenças e formas de
acesso estão no catálogo do vault (`biblioteca/catalogo.md`, aberto a partir do nó central).

| Obra (Autor) | Módulos |
|---|---|
| Cálculo (James Stewart) | 1 |
| Um Curso de Cálculo (Hamilton Luiz Guidorizzi) | 1 |
| Cálculo A (Diva Marília Flemming e Mirian Buss Gonçalves) | 1 |
| Calculus Volume 1 (Gilbert Strang e outros (OpenStax)) | 1 |
| Fundamentos Matemáticos para a Ciência da Computação (Judith L. Gersting) | 2 |
| Matemática Discreta e suas Aplicações (Kenneth H. Rosen) | 2 |
| Matemática Discreta para Computação e Informática (Paulo Blauth Menezes) | 2 |
| Lógica para Computação (Flávio Soares Corrêa da Silva, Marcelo Finger e Ana Cristina Vieira de Melo) | 2 |
| Matemática Discreta: uma introdução (Edward R. Scheinerman) | 2 |
| Mathematics for Computer Science (MIT OpenCourseWare 6.042J) (MIT OpenCourseWare) | 2 |
| Lógica de Programação: a construção de algoritmos e estruturas de dados (André Luiz Villar Forbellone e Henri Frederico Eberspächer) | 3 |
| Algoritmos e Programação de Computadores (Dilermando Piva Júnior e outros) | 3 |
| Fundamentos da Programação de Computadores (Ana Fernanda Gomes Ascencio e Edilene Aparecida Veneruchi de Campos) | 3 |
| Introdução a Algoritmos e Programação com Python: uma abordagem dirigida por testes (Raul Sidnei Wazlawick) | 3 |
| Algoritmos em Linguagem C (Paulo Feofiloff) | 3 |
| Álgebra Linear (José Luiz Boldrini e outros) | 4 |
| Álgebra Linear e suas Aplicações (Gilbert Strang) | 4 |
| Álgebra Linear com Aplicações (Howard Anton e Chris Rorres) | 4 |
| Linear Algebra (MIT OpenCourseWare 18.06SC) (Gilbert Strang (MIT OpenCourseWare)) | 4 |
| Estatística para Cursos de Engenharia e Informática (Pedro Alberto Barbetta, Marcelo Menezes Reis e Antonio Cezar Bornia) | 5 |
| Estatística Aplicada e Probabilidade para Engenheiros (Douglas C. Montgomery e George C. Runger) | 5 |
| Probabilidade e Estatística para Engenharia e Ciências (Ronald E. Walpole e outros) | 5 |
| Estatística Básica (Pedro A. Morettin e Wilton O. Bussab) | 5 |
| Introdução à Estatística (Mario F. Triola) | 5 |
| Introductory Statistics 2e (Barbara Illowsky, Susan Dean e outros (OpenStax)) | 5 |
| Física I: Mecânica (Hugh D. Young e Roger A. Freedman) | 6 |
| Fundamentos de Física, vol. 1 (David Halliday, Robert Resnick e Jearl Walker) | 6 |
| Curso de Física Básica 1 (H. Moysés Nussenzveig) | 6 |
| Física para Cientistas e Engenheiros, vol. 1 (Paul A. Tipler e Gene Mosca) | 6 |
| University Physics Volume 1 (Samuel J. Ling, Jeff Sanny, William Moebs e outros (OpenStax)) | 6 |
| Java: Como Programar (Paul Deitel e Harvey Deitel) | 7 |
| Programação Orientada a Objetos com Java: uma introdução prática usando o BlueJ (David J. Barnes e Michael Kölling) | 7 |
| Core Java, vol. I: Fundamentos (Cay S. Horstmann e Gary Cornell) | 7 |
| Use a Cabeça! Java (Kathy Sierra e Bert Bates) | 7 |
| UML 2: uma abordagem prática (Gilleanes T. A. Guedes) | 7 |
| Estruturas de Dados e seus Algoritmos (Jayme Luiz Szwarcfiter e Lilian Markenzon) | 8 |
| Estrutura de Dados e Algoritmos em C++ (Adam Drozdek) | 8 |
| Introdução a Estruturas de Dados: com técnicas de programação em C (Waldemar Celes, Renato Cerqueira e José Lucas Rangel) | 8 |
| Estruturas de Dados e Algoritmos em Java (Michael T. Goodrich e Roberto Tamassia) | 8 |
| Projeto de Algoritmos: com implementações em Java e C++ (Nivio Ziviani) | 8 |
| Open Data Structures (Pat Morin) | 8 |
| Engenharia de Software (Ian Sommerville) | 9, 16 |
| Engenharia de Software: uma abordagem profissional (Roger S. Pressman e Bruce R. Maxim) | 9, 16 |
| Engenharia de Software: teoria e prática (Shari Lawrence Pfleeger) | 9, 24 |
| Engenharia de Software: conceitos e práticas (Raul Sidnei Wazlawick) | 9 |
| Guide to the Software Engineering Body of Knowledge (SWEBOK) (IEEE Computer Society) | 9 |
| Engenharia de Software Moderna (Marco Tulio Valente) | 9, 16, 17, 18, 19, 21, 22, 23, 25 |
| Organização Estruturada de Computadores (Andrew S. Tanenbaum) | 10 |
| Arquitetura e Organização de Computadores (William Stallings) | 10 |
| Organização e Projeto de Computadores (David A. Patterson e John L. Hennessy) | 10 |
| Fundamentos de Arquitetura de Computadores (Raul Fernando Weber) | 10 |
| Introdução à Organização de Computadores (Mário A. Monteiro) | 10 |
| Algoritmos: Teoria e Prática (Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest e Clifford Stein) | 11 |
| Algoritmos (Sanjoy Dasgupta, Christos Papadimitriou e Umesh Vazirani) | 11 |
| Algorithm Design (Jon Kleinberg e Éva Tardos) | 11 |
| The Algorithm Design Manual (Steven S. Skiena) | 11 |
| Grafos: conceitos, algoritmos e aplicações (Marco Goldbarg e Elizabeth Goldbarg) | 11 |
| Conceitos de Linguagens de Programação (Robert W. Sebesta) | 12 |
| Linguagens de Programação: princípios e paradigmas (Allen B. Tucker e Robert Noonan) | 12 |
| Princípios de Linguagem de Programação (Ana Cristina Vieira de Melo e Flávio Soares Corrêa da Silva) | 12 |
| Programming Language Pragmatics (Michael L. Scott) | 12 |
| Sistemas de Banco de Dados (Ramez Elmasri e Shamkant B. Navathe) | 13 |
| Sistema de Banco de Dados (Abraham Silberschatz, Henry F. Korth e S. Sudarshan) | 13 |
| Projeto de Banco de Dados (Carlos Alberto Heuser) | 13 |
| Introdução a Sistemas de Bancos de Dados (C. J. Date) | 13 |
| Sistemas de Gerenciamento de Banco de Dados (Raghu Ramakrishnan e Johannes Gehrke) | 13 |
| NoSQL Essencial (Pramod J. Sadalage e Martin Fowler) | 13 |
| Sistemas Operacionais Modernos (Andrew S. Tanenbaum e Herbert Bos) | 14 |
| Fundamentos de Sistemas Operacionais (Abraham Silberschatz, Peter B. Galvin e Greg Gagne) | 14 |
| Sistemas Operacionais (Harvey M. Deitel, Paul J. Deitel e David R. Choffnes) | 14 |
| Arquitetura de Sistemas Operacionais (Francis B. Machado e Luiz Paulo Maia) | 14 |
| Operating Systems: Three Easy Pieces (Remzi H. Arpaci-Dusseau e Andrea C. Arpaci-Dusseau) | 14 |
| Redes de Computadores e a Internet: uma abordagem top-down (James F. Kurose e Keith W. Ross) | 15 |
| Redes de Computadores (Andrew S. Tanenbaum e David Wetherall) | 15 |
| Redes de Computadores e Internet (Douglas E. Comer) | 15 |
| Comunicação de Dados e Redes de Computadores (Behrouz A. Forouzan) | 15 |
| Computer Networks: A Systems Approach (Larry Peterson e Bruce Davie) | 15 |
| Desenvolvimento de Software com Scrum (Mike Cohn) | 16 |
| Programação Extrema (XP) Explicada (Kent Beck) | 16 |
| Metodologias Ágeis: engenharia de software sob medida (José Henrique Teixeira de Carvalho Sbrocco e Paulo Cesar de Macedo) | 16 |
| Introdução ao RUP: Rational Unified Process (Philippe Kruchten) | 16 |
| The Scrum Guide (Ken Schwaber e Jeff Sutherland) | 16, 29 |
| Engenharia de Requisitos (Sheila Reinehr) | 17 |
| Engenharia de Requisitos: software orientado ao negócio (Carlos Eduardo Vazquez e Guilherme Siqueira Simões) | 17 |
| Escrevendo Casos de Uso Eficazes (Alistair Cockburn) | 17 |
| Software Requirements (Karl E. Wiegers e Joy Beatty) | 17 |
| Requirements Engineering: Processes and Techniques (Gerald Kotonya e Ian Sommerville) | 17 |
| User Story Mapping (Jeff Patton e Peter Economy) | 17 |
| Utilizando UML e Padrões (Craig Larman) | 18, 19 |
| UML Essencial (Martin Fowler) | 18 |
| UML: Guia do Usuário (Grady Booch, James Rumbaugh e Ivar Jacobson) | 18 |
| Princípios de Análise e Projeto de Sistemas com UML (Eduardo Bezerra) | 18 |
| Análise e Design Orientados a Objetos para Sistemas de Informação (Raul Sidnei Wazlawick) | 18 |
| Padrões de Projeto: soluções reutilizáveis de software orientado a objetos (Erich Gamma, Richard Helm, Ralph Johnson e John Vlissides) | 19 |
| Refatoração para Padrões (Joshua Kerievsky) | 19 |
| Explicando Padrões de Projeto (Alan Shalloway e James R. Trott) | 19 |
| Código Limpo (Robert C. Martin) | 19 |
| Use a Cabeça! Padrões de Projetos (Eric Freeman, Elisabeth Freeman, Kathy Sierra e Bert Bates) | 19 |
| Design de Interação: além da interação humano-computador (Yvonne Rogers, Helen Sharp e Jennifer Preece) | 20 |
| Interação Humano-Computador (Simone Diniz Junqueira Barbosa e Bruno Santana da Silva) | 20 |
| Ergonomia e Usabilidade: conhecimentos, métodos e aplicações (Walter Cybis, Adriana Holtz Betiol e Richard Faust) | 20 |
| Usabilidade na Web (Jakob Nielsen e Hoa Loranger) | 20 |
| Design e Avaliação de Interfaces Humano-Computador (Heloísa Vieira da Rocha e Maria Cecília C. Baranauskas (NIED/Unicamp)) | 20 |
| Introdução ao Teste de Software (Márcio Delamaro, José Carlos Maldonado e Mario Jino) | 21 |
| The Art of Software Testing (Glenford J. Myers, Corey Sandler e Tom Badgett) | 21 |
| TDD: Desenvolvimento Guiado por Testes (Kent Beck) | 21 |
| Teste e Análise de Software: processos, princípios e técnicas (Mauro Pezzè e Michal Young) | 21 |
| xUnit Test Patterns (Gerard Meszaros) | 21 |
| Software Architecture in Practice (Len Bass, Paul Clements e Rick Kazman) | 22 |
| Padrões de Arquitetura de Aplicações Corporativas (Martin Fowler) | 22 |
| Arquitetura Limpa (Robert C. Martin) | 22 |
| Documenting Software Architectures: Views and Beyond (Paul Clements e outros) | 22 |
| Pattern-Oriented Software Architecture, vol. 1 (Frank Buschmann e outros) | 22 |
| Essential Software Architecture (Ian Gorton) | 22 |
| Entrega Contínua (Jez Humble e David Farley) | 23 |
| Configuration Management: Principles and Practice (Anne Mette Jonassen Hass) | 23 |
| Gerência de Configuração: técnicas e práticas no desenvolvimento do software (Leonardo Molinari) | 23 |
| Manual de DevOps (Gene Kim, Jez Humble, Patrick Debois e John Willis) | 23 |
| Software Configuration Management Patterns (Stephen P. Berczuk e Brad Appleton) | 23 |
| Pro Git (Scott Chacon e Ben Straub) | 23 |
| Qualidade de Software: aprenda as metodologias e técnicas mais modernas para o desenvolvimento de software (André Koscianski e Michel dos Santos Soares) | 24 |
| Qualidade de Software (Aline Zanin e outros) | 24 |
| Software Metrics: A Rigorous and Practical Approach (Norman Fenton e Shari Lawrence Pfleeger) | 24 |
| Metrics and Models in Software Quality Engineering (Stephen H. Kan) | 24 |
| Refatoração: aperfeiçoando o projeto de código existente (Martin Fowler) | 25 |
| Software Maintenance: Concepts and Practice (Penny Grubb e Armstrong A. Takang) | 25 |
| Code Complete (Steve McConnell) | 25 |
| Evolving Software Systems (Tom Mens, Alexander Serebrenik e Anthony Cleve) | 25 |
| Object-Oriented Reengineering Patterns (Serge Demeyer, Stéphane Ducasse e Oscar Nierstrasz) | 25 |
| JavaScript: O Guia Definitivo (David Flanagan) | 26 |
| Engenharia Web (Roger S. Pressman e David Lowe) | 26 |
| HTML5: a linguagem de marcação que revolucionou a web (Maurício Samy Silva) | 26 |
| JSON Básico (Ben Smith) | 26 |
| Desenvolvimento de Software II: introdução ao desenvolvimento web com HTML, CSS, JavaScript e PHP (Evandro Manara Miletto e Silvia de Castro Bertagnolli) | 26 |
| Java para Web: desenvolvimento de aplicações (William Pereira Alves) | 26 |
| Android para Programadores: uma abordagem baseada em aplicativos (Paul Deitel, Harvey Deitel e coautores) | 27 |
| Desenvolvimento para Dispositivos Móveis (Diego Bittencourt de Oliveira e outros) | 27 |
| Google Android: aprenda a criar aplicações para dispositivos móveis com o Android SDK (Ricardo R. Lecheta) | 27 |
| Writing Mobile Code: Essential Software Engineering for Building Mobile Applications (Ivo Salmre) | 27 |
| Use a Cabeça! Desenvolvendo para Android (Dawn Griffiths e David Griffiths) | 27 |
| Sistemas Distribuídos: conceitos e projeto (George Coulouris, Jean Dollimore e Tim Kindberg) | 28 |
| Sistemas Distribuídos: princípios e paradigmas (Andrew S. Tanenbaum e Maarten van Steen) | 28 |
| Construindo Software como Serviço (SaaS): uma abordagem ágil usando computação em nuvem (Armando Fox e David Patterson) | 28 |
| Distributed Systems (Maarten van Steen e Andrew S. Tanenbaum) | 28 |
| Um Guia do Conhecimento em Gerenciamento de Projetos (Guia PMBOK) (Project Management Institute) | 29 |
| Gestão Ágil de Projetos (Robson Camargo e Thomaz Ribas) | 29 |
| Scrum Essencial: um guia prático para o mais popular processo ágil (Kenneth S. Rubin) | 29 |
| Gerenciamento de Projetos: estabelecendo diferenciais competitivos (Ricardo Viana Vargas) | 29 |
| Análise de Pontos de Função: medição, estimativas e gerenciamento de projetos de software (Carlos Eduardo Vazquez, Guilherme Siqueira Simões e Renato Machado Albert) | 29 |
| Scrum em Ação: gerenciamento de desenvolvimento ágil de projetos de software (Andrew Pham e Phuong-Van Pham) | 29 |
| Metodologia de Pesquisa para Ciência da Computação (Raul Sidnei Wazlawick) | 30 |
| Experimentation in Software Engineering: An Introduction (Claes Wohlin e outros) | 30 |
| Basics of Software Engineering Experimentation (Natalia Juristo e Ana M. Moreno) | 30 |
| Evidence-Based Software Engineering and Systematic Reviews (Barbara Kitchenham, David Budgen e Pearl Brereton) | 30 |
| Estudo de Caso: planejamento e métodos (Robert K. Yin) | 30 |
| Inteligência Artificial (Stuart Russell e Peter Norvig) | 31 |
| Inteligência Artificial: uma abordagem de aprendizado de máquina (Katti Faceli e outros) | 31 |
| Redes Neurais: princípios e prática (Simon Haykin) | 31 |
| Machine Learning (Tom M. Mitchell) | 31 |
| Mãos à Obra: Aprendizado de Máquina com Scikit-Learn, Keras & TensorFlow (Aurélien Géron) | 31 |
| Ética em Computação (Paulo Cesar Masiero) | 32 |
| Ética Profissional (Antônio Lopes de Sá) | 32 |
| Ética na Computação: uma abordagem baseada em casos (Robert N. Barger) | 32 |
| Direito Digital (Patrícia Peck Pinheiro) | 32 |
| Ethics for the Information Age (Michael J. Quinn) | 32 |
| Empreendedorismo (Robert D. Hisrich, Michael P. Peters e Dean A. Shepherd) | 33 |
| Inovação e Empreendedorismo (John Bessant e Joe Tidd) | 33 |
| Empreendedorismo: transformando ideias em negócios (José Dornelas) | 33 |
| Gestão da Inovação (Joe Tidd e John Bessant) | 33 |
| Business Model Generation (Alexander Osterwalder e Yves Pigneur) | 33 |

## Fontes

Ementas, grades e bibliografias consolidadas a partir dos projetos pedagógicos (PPC) de
bacharelados em Engenharia de Software de cinco universidades públicas. Entraram no
percurso as disciplinas obrigatórias presentes na maioria delas; optativas e disciplinas
de uma só instituição ficaram de fora, salvo o ciclo básico de engenharia. Cálculo I,
Álgebra Linear e Física I são obrigatórias só na UnB (na UFMS, Cálculo e Álgebra Linear
são optativas); foram mantidas como ciclo básico. Estágio, TCC e projetos integradores não
entram, por exigirem supervisão. Todos os links foram abertos em 2026-10.

- Universidade de Brasília (UnB), Faculdade UnB Gama: PPC do Bacharelado em Engenharia de Software (2023, versão de 12/2025), https://sigaa.unb.br/sigaa/verProducao?idProducao=3796078&key=607465e55d349559b6767e8b05cb2515 — página da matriz: https://software.unb.br/matriz-curricular/ (verificado em 2026-10).
- Universidade Federal do Ceará (UFC), Campus Quixadá: PPC de Engenharia de Software 2023, https://es.quixada.ufc.br/wp-content/uploads/2023/05/PPC-ES-2023.pdf — página dos PPCs: https://es.quixada.ufc.br/documentos/projeto-pedagogico-de-curso-ppc/ (verificado em 2026-10).
- Universidade Federal do Cariri (UFCA), Centro de Ciências e Tecnologia: PPC do Bacharelado em Engenharia de Software (2024), https://documentos.ufca.edu.br/doc/cct-ufca-projeto-pedagogico-do-curso-engenharia-de-software-2024 (verificado em 2026-10).
- Universidade do Estado de Santa Catarina (UDESC), CEAVI: Projeto Pedagógico de Engenharia de Software (2022), https://www.udesc.br/arquivos/ceavi/id_cpmenu/139/Projeto_Pedag_gico___Engenharia_de_Software_16867772331217_139.pdf (verificado em 2026-10).
- Universidade Federal de Mato Grosso do Sul (UFMS), Faculdade de Computação: PPC de Engenharia de Software (Resolução nº 1.308-Cograd/UFMS, de 8/12/2025), https://www.facom.ufms.br/wp-content/uploads/2026/02/PPC_2025.pdf — página do curso: https://www.facom.ufms.br/engenharia-de-software/ (verificado em 2026-10).
- Diretrizes Curriculares Nacionais dos cursos de Computação, incluindo Engenharia de Software (Resolução CNE/CES nº 5, de 16/11/2016), cópia em https://abmes.org.br/public/arquivos/legislacoes/Res-CES-CNE-005-2016-11-16.pdf (verificado em 2026-10).
- Sociedade Brasileira de Computação (SBC): Referenciais de Formação para os Cursos de Graduação em Computação (2017), https://books-sol.sbc.org.br/index.php/sbc/catalog/download/134/586/904?inline=1 (verificado em 2026-10).

## Módulo 1 — Cálculo I

**Depende de:** nenhum

### Objetivo

Dominar funções de uma variável, limites, derivadas e integrais, e usá-los para modelar taxas de variação e acumulação.

### Tópicos

- [ ] 1. Números reais, funções e seus gráficos; funções compostas e inversas
- [ ] 2. Funções trigonométricas, exponenciais e logarítmicas
- [ ] 3. Limites, limites laterais e limites no infinito
- [ ] 4. Continuidade e Teorema do Valor Intermediário
- [ ] 5. Derivada: definição, reta tangente e regras de derivação
- [ ] 6. Regra da cadeia, derivação implícita e taxas relacionadas
- [ ] 7. Máximos e mínimos, Teorema do Valor Médio e regras de L'Hospital
- [ ] 8. Concavidade, esboço de gráficos e problemas de otimização
- [ ] 9. Integral definida, primitivas e Teorema Fundamental do Cálculo
- [ ] 10. Técnicas de integração: substituição, por partes e frações parciais
- [ ] 11. Aplicações da integral: áreas, volumes e comprimento de curvas

### Leituras

- Básica: Cálculo (James Stewart) — v. 1.
- Básica: Um Curso de Cálculo (Hamilton Luiz Guidorizzi) — v. 1.
- Complementar: Cálculo A (Diva Marília Flemming e Mirian Buss Gonçalves).
- Alternativa aberta: Calculus Volume 1 (Gilbert Strang e outros (OpenStax)).

### Resultado esperado

Calcular limites, derivadas e integrais de funções elementares e resolver problemas de otimização e de área.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-01.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2 — Matemática Discreta e Lógica]]

## Módulo 2 — Matemática Discreta e Lógica

**Depende de:** nenhum

### Objetivo

Construir a base matemática da computação: lógica, demonstração, conjuntos, relações, contagem e grafos.

### Tópicos

- [ ] 1. Lógica proposicional: conectivos, tabelas-verdade e equivalências
- [ ] 2. Lógica de predicados e quantificadores
- [ ] 3. Técnicas de demonstração: direta, contraposição, absurdo e indução
- [ ] 4. Conjuntos, operações e cardinalidade
- [ ] 5. Relações: propriedades, fechos, equivalência e ordem
- [ ] 6. Funções: injetoras, sobrejetoras, bijetoras e composição
- [ ] 7. Somatórios, sequências e recorrências simples
- [ ] 8. Teoria dos números: divisibilidade, primos e aritmética modular
- [ ] 9. Contagem: princípios aditivo e multiplicativo, permutações e combinações
- [ ] 10. Grafos e árvores: terminologia, conectividade e isomorfismo
- [ ] 11. Álgebra booleana e sua relação com circuitos lógicos

### Leituras

- Básica: Fundamentos Matemáticos para a Ciência da Computação (Judith L. Gersting).
- Básica: Matemática Discreta e suas Aplicações (Kenneth H. Rosen).
- Complementar: Matemática Discreta para Computação e Informática (Paulo Blauth Menezes).
- Complementar: Lógica para Computação (Flávio Soares Corrêa da Silva, Marcelo Finger e Ana Cristina Vieira de Melo).
- Complementar: Matemática Discreta: uma introdução (Edward R. Scheinerman).
- Alternativa aberta: Mathematics for Computer Science (MIT OpenCourseWare 6.042J) (MIT OpenCourseWare).

### Resultado esperado

Escrever demonstrações simples, formalizar enunciados em lógica e resolver problemas de contagem, relações e grafos.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-02.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 3 — Algoritmos e Programação|Módulo 3 — Algoritmos e Programação]]

## Módulo 3 — Algoritmos e Programação

**Depende de:** nenhum

### Objetivo

Aprender a resolver problemas por meio de algoritmos e implementá-los em uma linguagem de programação estruturada.

### Tópicos

- [ ] 1. Processo de solução de problemas e representação de algoritmos
- [ ] 2. Variáveis, constantes, tipos primitivos e operadores
- [ ] 3. Expressões lógicas e estruturas condicionais
- [ ] 4. Estruturas de repetição
- [ ] 5. Funções, procedimentos e passagem de parâmetros
- [ ] 6. Vetores, matrizes e cadeias de caracteres
- [ ] 7. Registros e tipos estruturados
- [ ] 8. Ponteiros e alocação dinâmica de memória
- [ ] 9. Leitura e escrita de arquivos de texto
- [ ] 10. Depuração de programas e testes unitários iniciais

### Leituras

- Básica: Lógica de Programação: a construção de algoritmos e estruturas de dados (André Luiz Villar Forbellone e Henri Frederico Eberspächer).
- Básica: Algoritmos e Programação de Computadores (Dilermando Piva Júnior e outros).
- Complementar: Fundamentos da Programação de Computadores (Ana Fernanda Gomes Ascencio e Edilene Aparecida Veneruchi de Campos).
- Complementar: Introdução a Algoritmos e Programação com Python: uma abordagem dirigida por testes (Raul Sidnei Wazlawick).
- Complementar: Algoritmos em Linguagem C (Paulo Feofiloff).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Escrever, testar e depurar programas de pequeno porte que usem decisões, repetições, funções, vetores e arquivos.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-03.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 4 — Álgebra Linear|Módulo 4 — Álgebra Linear]]

## Módulo 4 — Álgebra Linear

**Depende de:** nenhum

### Objetivo

Operar com matrizes, sistemas lineares e espaços vetoriais, ferramentas de computação gráfica, aprendizado de máquina e métodos numéricos.

### Tópicos

- [ ] 1. Matrizes e operações matriciais
- [ ] 2. Sistemas de equações lineares e eliminação de Gauss
- [ ] 3. Determinantes e matriz inversa
- [ ] 4. Espaços e subespaços vetoriais
- [ ] 5. Dependência e independência linear
- [ ] 6. Base e dimensão
- [ ] 7. Transformações lineares e suas matrizes
- [ ] 8. Autovalores e autovetores
- [ ] 9. Diagonalização de operadores
- [ ] 10. Produto interno, ortogonalidade e projeções

### Leituras

- Básica: Álgebra Linear (José Luiz Boldrini e outros).
- Básica: Álgebra Linear e suas Aplicações (Gilbert Strang).
- Complementar: Álgebra Linear com Aplicações (Howard Anton e Chris Rorres).
- Alternativa aberta: Linear Algebra (MIT OpenCourseWare 18.06SC) (Gilbert Strang (MIT OpenCourseWare)).

### Resultado esperado

Resolver sistemas lineares, decidir sobre independência e base e calcular autovalores e diagonalizações.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-04.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 5 — Probabilidade e Estatística|Módulo 5 — Probabilidade e Estatística]]

## Módulo 5 — Probabilidade e Estatística

**Depende de:** [[#Módulo 1 — Cálculo I|Módulo 1]], [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2]]

### Objetivo

Descrever dados, modelar incerteza e tirar conclusões por inferência estatística, base para medição e experimentação em software.

### Tópicos

- [ ] 1. Estatística descritiva: tendência central, dispersão e gráficos
- [ ] 2. Análise combinatória aplicada à probabilidade
- [ ] 3. Probabilidade: axiomas, probabilidade condicional e independência
- [ ] 4. Teorema de Bayes
- [ ] 5. Variáveis aleatórias discretas e contínuas
- [ ] 6. Distribuições binomial, Poisson, normal e exponencial
- [ ] 7. Amostragem e distribuições amostrais
- [ ] 8. Estimação e intervalos de confiança
- [ ] 9. Testes de hipóteses e erros dos tipos I e II
- [ ] 10. Correlação e regressão linear simples
- [ ] 11. Testes de aderência (qui-quadrado)

### Leituras

- Básica: Estatística para Cursos de Engenharia e Informática (Pedro Alberto Barbetta, Marcelo Menezes Reis e Antonio Cezar Bornia).
- Básica: Estatística Aplicada e Probabilidade para Engenheiros (Douglas C. Montgomery e George C. Runger).
- Complementar: Probabilidade e Estatística para Engenharia e Ciências (Ronald E. Walpole e outros).
- Complementar: Estatística Básica (Pedro A. Morettin e Wilton O. Bussab).
- Complementar: Introdução à Estatística (Mario F. Triola).
- Alternativa aberta: Introductory Statistics 2e (Barbara Illowsky, Susan Dean e outros (OpenStax)).

### Resultado esperado

Resumir um conjunto de dados, calcular probabilidades com as distribuições usuais e conduzir intervalos de confiança e testes de hipóteses.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-05.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 6 — Física I|Módulo 6 — Física I]]

## Módulo 6 — Física I

**Depende de:** [[#Módulo 1 — Cálculo I|Módulo 1]]

### Objetivo

Estudar a mecânica clássica com o ferramental do cálculo, como parte do núcleo comum de engenharia.

### Tópicos

- [ ] 1. Unidades, grandezas físicas e vetores
- [ ] 2. Movimento retilíneo
- [ ] 3. Movimento em duas e três dimensões
- [ ] 4. Leis de Newton do movimento
- [ ] 5. Aplicações das leis de Newton e atrito
- [ ] 6. Trabalho e energia cinética
- [ ] 7. Energia potencial e conservação da energia
- [ ] 8. Momento linear, impulso e colisões
- [ ] 9. Rotação de corpos rígidos
- [ ] 10. Dinâmica do movimento de rotação

### Leituras

- Básica: Física I: Mecânica (Hugh D. Young e Roger A. Freedman).
- Básica: Fundamentos de Física, vol. 1 (David Halliday, Robert Resnick e Jearl Walker).
- Complementar: Curso de Física Básica 1 (H. Moysés Nussenzveig).
- Complementar: Física para Cientistas e Engenheiros, vol. 1 (Paul A. Tipler e Gene Mosca).
- Alternativa aberta: University Physics Volume 1 (Samuel J. Ling, Jeff Sanny, William Moebs e outros (OpenStax)).

### Resultado esperado

Resolver problemas de cinemática e dinâmica de partículas e corpos rígidos usando leis de Newton e conservação.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-06.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 7 — Programação Orientada a Objetos|Módulo 7 — Programação Orientada a Objetos]]

## Módulo 7 — Programação Orientada a Objetos

**Depende de:** [[#Módulo 3 — Algoritmos e Programação|Módulo 3]]

### Objetivo

Projetar e implementar programas no paradigma orientado a objetos.

### Tópicos

- [ ] 1. Classes, objetos, atributos e métodos
- [ ] 2. Construtores e ciclo de vida de objetos
- [ ] 3. Encapsulamento e modificadores de acesso
- [ ] 4. Herança e reutilização
- [ ] 5. Polimorfismo e ligação dinâmica
- [ ] 6. Classes abstratas e interfaces
- [ ] 7. Tratamento de exceções
- [ ] 8. Coleções e classes genéricas
- [ ] 9. Noções de diagrama de classes UML
- [ ] 10. Desenvolvimento de um pequeno sistema orientado a objetos

### Leituras

- Básica: Java: Como Programar (Paul Deitel e Harvey Deitel).
- Básica: Programação Orientada a Objetos com Java: uma introdução prática usando o BlueJ (David J. Barnes e Michael Kölling).
- Complementar: Core Java, vol. I: Fundamentos (Cay S. Horstmann e Gary Cornell).
- Complementar: Use a Cabeça! Java (Kathy Sierra e Bert Bates).
- Complementar: UML 2: uma abordagem prática (Gilleanes T. A. Guedes).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Implementar um sistema pequeno com classes, herança, interfaces e tratamento de exceções, e representá-lo em diagrama de classes.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-07.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 8 — Estruturas de Dados|Módulo 8 — Estruturas de Dados]]

## Módulo 8 — Estruturas de Dados

**Depende de:** [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2]], [[#Módulo 3 — Algoritmos e Programação|Módulo 3]]

### Objetivo

Conhecer, implementar e escolher estruturas de dados conforme o custo das operações.

### Tópicos

- [ ] 1. Noções de análise de algoritmos e notação assintótica
- [ ] 2. Recursividade
- [ ] 3. Tipos abstratos de dados
- [ ] 4. Listas sequenciais e encadeadas
- [ ] 5. Pilhas e filas
- [ ] 6. Algoritmos de ordenação e busca
- [ ] 7. Árvores binárias e árvores binárias de busca
- [ ] 8. Árvores balanceadas
- [ ] 9. Filas de prioridade e heaps
- [ ] 10. Tabelas de dispersão (hash) e tratamento de colisões
- [ ] 11. Representação de grafos e percursos em largura e profundidade

### Leituras

- Básica: Estruturas de Dados e seus Algoritmos (Jayme Luiz Szwarcfiter e Lilian Markenzon).
- Básica: Estrutura de Dados e Algoritmos em C++ (Adam Drozdek).
- Complementar: Introdução a Estruturas de Dados: com técnicas de programação em C (Waldemar Celes, Renato Cerqueira e José Lucas Rangel).
- Complementar: Estruturas de Dados e Algoritmos em Java (Michael T. Goodrich e Roberto Tamassia).
- Complementar: Projeto de Algoritmos: com implementações em Java e C++ (Nivio Ziviani).
- Alternativa aberta: Open Data Structures (Pat Morin).

### Resultado esperado

Implementar listas, pilhas, filas, árvores, heaps e tabelas hash e justificar a escolha de cada uma pelo custo das operações.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-08.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 9 — Introdução à Engenharia de Software|Módulo 9 — Introdução à Engenharia de Software]]

## Módulo 9 — Introdução à Engenharia de Software

**Depende de:** [[#Módulo 3 — Algoritmos e Programação|Módulo 3]]

### Objetivo

Entender o que é engenharia de software, seu histórico, suas áreas de conhecimento e o papel profissional do engenheiro de software.

### Tópicos

- [ ] 1. Software, crise do software e histórico da engenharia de software
- [ ] 2. Características e responsabilidades do profissional de engenharia de software
- [ ] 3. Ciclo de vida do software
- [ ] 4. Modelos de processo: cascata, incremental, espiral e ágeis
- [ ] 5. Visão geral de requisitos, projeto, construção e testes
- [ ] 6. Visão geral de manutenção, configuração e qualidade
- [ ] 7. Áreas de conhecimento do SWEBOK
- [ ] 8. Ética e responsabilidade profissional
- [ ] 9. Software livre e código aberto

### Leituras

- Básica: Engenharia de Software (Ian Sommerville).
- Básica: Engenharia de Software: uma abordagem profissional (Roger S. Pressman e Bruce R. Maxim).
- Complementar: Engenharia de Software: teoria e prática (Shari Lawrence Pfleeger).
- Complementar: Engenharia de Software: conceitos e práticas (Raul Sidnei Wazlawick).
- Complementar: Guide to the Software Engineering Body of Knowledge (SWEBOK) (IEEE Computer Society).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 1.

### Resultado esperado

Explicar as atividades do desenvolvimento de software e comparar os principais modelos de processo.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-09.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 10 — Arquitetura e Organização de Computadores|Módulo 10 — Arquitetura e Organização de Computadores]]

## Módulo 10 — Arquitetura e Organização de Computadores

**Depende de:** [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2]], [[#Módulo 3 — Algoritmos e Programação|Módulo 3]]

### Objetivo

Entender como o hardware executa programas: representação de dados, processador, memória e entrada e saída.

### Tópicos

- [ ] 1. Sistemas de numeração e aritmética binária
- [ ] 2. Representação em ponto fixo e ponto flutuante
- [ ] 3. Portas lógicas e circuitos combinacionais e sequenciais
- [ ] 4. Organização de von Neumann: CPU, memória e E/S
- [ ] 5. Conjunto de instruções e modos de endereçamento
- [ ] 6. Linguagem de montagem
- [ ] 7. Interrupções e exceções
- [ ] 8. Hierarquia de memória e memória cache
- [ ] 9. Barramentos e periféricos
- [ ] 10. Arquiteturas RISC e CISC e pipeline
- [ ] 11. Noções de paralelismo e multiprocessadores

### Leituras

- Básica: Organização Estruturada de Computadores (Andrew S. Tanenbaum).
- Básica: Arquitetura e Organização de Computadores (William Stallings).
- Complementar: Organização e Projeto de Computadores (David A. Patterson e John L. Hennessy).
- Complementar: Fundamentos de Arquitetura de Computadores (Raul Fernando Weber).
- Complementar: Introdução à Organização de Computadores (Mário A. Monteiro).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Descrever o caminho de uma instrução pelo processador e explicar o impacto de memória cache e pipeline no desempenho.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-10.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 11 — Projeto e Análise de Algoritmos|Módulo 11 — Projeto e Análise de Algoritmos]]

## Módulo 11 — Projeto e Análise de Algoritmos

**Depende de:** [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2]], [[#Módulo 8 — Estruturas de Dados|Módulo 8]]

### Objetivo

Analisar a eficiência de algoritmos e projetá-los com as técnicas clássicas.

### Tópicos

- [ ] 1. Análise assintótica de pior caso e caso médio
- [ ] 2. Notações O, ômega e teta
- [ ] 3. Recorrências e análise de algoritmos recursivos
- [ ] 4. Força bruta e divisão e conquista
- [ ] 5. Algoritmos gulosos
- [ ] 6. Programação dinâmica
- [ ] 7. Algoritmos em grafos: ordenação topológica e árvores geradoras mínimas
- [ ] 8. Caminhos mínimos
- [ ] 9. Classes P e NP e NP-completude
- [ ] 10. Reduções entre problemas e noções de heurísticas

### Leituras

- Básica: Algoritmos: Teoria e Prática (Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest e Clifford Stein).
- Básica: Algoritmos (Sanjoy Dasgupta, Christos Papadimitriou e Umesh Vazirani).
- Complementar: Algorithm Design (Jon Kleinberg e Éva Tardos).
- Complementar: The Algorithm Design Manual (Steven S. Skiena).
- Complementar: Grafos: conceitos, algoritmos e aplicações (Marco Goldbarg e Elizabeth Goldbarg).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Provar a complexidade de algoritmos simples e escolher a técnica de projeto adequada a um problema.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-11.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 12 — Paradigmas de Programação|Módulo 12 — Paradigmas de Programação]]

## Módulo 12 — Paradigmas de Programação

**Depende de:** [[#Módulo 7 — Programação Orientada a Objetos|Módulo 7]]

### Objetivo

Comparar paradigmas e conceitos de linguagens para escolher e aprender linguagens com critério.

### Tópicos

- [ ] 1. Critérios de avaliação e evolução das linguagens
- [ ] 2. Sintaxe e semântica; noções de análise léxica e sintática
- [ ] 3. Nomes, vinculações, escopo e tempo de vida
- [ ] 4. Tipos de dados e verificação de tipos
- [ ] 5. Expressões e estruturas de controle
- [ ] 6. Subprogramas e passagem de parâmetros
- [ ] 7. Abstração de dados e orientação a objetos
- [ ] 8. Programação funcional
- [ ] 9. Programação lógica
- [ ] 10. Concorrência e tratamento de exceções nas linguagens

### Leituras

- Básica: Conceitos de Linguagens de Programação (Robert W. Sebesta).
- Básica: Linguagens de Programação: princípios e paradigmas (Allen B. Tucker e Robert Noonan).
- Complementar: Princípios de Linguagem de Programação (Ana Cristina Vieira de Melo e Flávio Soares Corrêa da Silva).
- Complementar: Programming Language Pragmatics (Michael L. Scott).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Explicar como diferentes linguagens tratam tipos, escopo e abstração e escrever programas simples nos paradigmas funcional e lógico.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-12.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 13 — Banco de Dados|Módulo 13 — Banco de Dados]]

## Módulo 13 — Banco de Dados

**Depende de:** [[#Módulo 2 — Matemática Discreta e Lógica|Módulo 2]], [[#Módulo 3 — Algoritmos e Programação|Módulo 3]]

### Objetivo

Modelar, projetar e consultar bancos de dados relacionais e conhecer alternativas não relacionais.

### Tópicos

- [ ] 1. Conceitos de banco de dados e de SGBD
- [ ] 2. Arquitetura de um SGBD e independência de dados
- [ ] 3. Modelo entidade-relacionamento
- [ ] 4. Modelo relacional e mapeamento ER-relacional
- [ ] 5. Álgebra relacional
- [ ] 6. SQL: definição e manipulação de dados
- [ ] 7. Consultas SQL avançadas, visões e restrições de integridade
- [ ] 8. Dependências funcionais e normalização
- [ ] 9. Indexação e noções de processamento de consultas
- [ ] 10. Transações e controle de concorrência
- [ ] 11. Bancos de dados não relacionais (NoSQL)

### Leituras

- Básica: Sistemas de Banco de Dados (Ramez Elmasri e Shamkant B. Navathe).
- Básica: Sistema de Banco de Dados (Abraham Silberschatz, Henry F. Korth e S. Sudarshan).
- Complementar: Projeto de Banco de Dados (Carlos Alberto Heuser).
- Complementar: Introdução a Sistemas de Bancos de Dados (C. J. Date).
- Complementar: Sistemas de Gerenciamento de Banco de Dados (Raghu Ramakrishnan e Johannes Gehrke).
- Complementar: NoSQL Essencial (Pramod J. Sadalage e Martin Fowler).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Modelar um domínio em ER, gerar o esquema relacional normalizado e escrever consultas SQL sobre ele.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-13.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 14 — Sistemas Operacionais|Módulo 14 — Sistemas Operacionais]]

## Módulo 14 — Sistemas Operacionais

**Depende de:** [[#Módulo 10 — Arquitetura e Organização de Computadores|Módulo 10]]

### Objetivo

Entender como o sistema operacional gerencia processos, memória, arquivos e dispositivos.

### Tópicos

- [ ] 1. Histórico, funções e tipos de sistemas operacionais
- [ ] 2. Estrutura do sistema operacional e chamadas de sistema
- [ ] 3. Processos e threads
- [ ] 4. Escalonamento de processos
- [ ] 5. Concorrência e sincronização
- [ ] 6. Deadlocks
- [ ] 7. Gerenciamento de memória e paginação
- [ ] 8. Memória virtual
- [ ] 9. Sistemas de arquivos
- [ ] 10. Gerenciamento de entrada e saída
- [ ] 11. Noções de virtualização e segurança

### Leituras

- Básica: Sistemas Operacionais Modernos (Andrew S. Tanenbaum e Herbert Bos).
- Básica: Fundamentos de Sistemas Operacionais (Abraham Silberschatz, Peter B. Galvin e Greg Gagne).
- Complementar: Sistemas Operacionais (Harvey M. Deitel, Paul J. Deitel e David R. Choffnes).
- Complementar: Arquitetura de Sistemas Operacionais (Francis B. Machado e Luiz Paulo Maia).
- Alternativa aberta: Operating Systems: Three Easy Pieces (Remzi H. Arpaci-Dusseau e Andrea C. Arpaci-Dusseau).

### Resultado esperado

Escrever programas concorrentes corretos e explicar decisões de escalonamento e de gerência de memória.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-14.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 15 — Redes de Computadores|Módulo 15 — Redes de Computadores]]

## Módulo 15 — Redes de Computadores

**Depende de:** [[#Módulo 14 — Sistemas Operacionais|Módulo 14]]

### Objetivo

Compreender a arquitetura e os protocolos da Internet do ponto de vista de quem desenvolve aplicações.

### Tópicos

- [ ] 1. Organização das redes e comutação de pacotes
- [ ] 2. Modelos de referência OSI e TCP/IP
- [ ] 3. Camada de aplicação: HTTP, DNS e correio eletrônico
- [ ] 4. Modelos cliente-servidor e P2P; programação com sockets
- [ ] 5. Camada de transporte: UDP e TCP
- [ ] 6. Controle de congestionamento
- [ ] 7. Camada de rede: protocolo IP e endereçamento
- [ ] 8. Algoritmos e protocolos de roteamento
- [ ] 9. Camada de enlace e redes locais
- [ ] 10. Redes sem fio
- [ ] 11. Noções de segurança em redes

### Leituras

- Básica: Redes de Computadores e a Internet: uma abordagem top-down (James F. Kurose e Keith W. Ross).
- Básica: Redes de Computadores (Andrew S. Tanenbaum e David Wetherall).
- Complementar: Redes de Computadores e Internet (Douglas E. Comer).
- Complementar: Comunicação de Dados e Redes de Computadores (Behrouz A. Forouzan).
- Alternativa aberta: Computer Networks: A Systems Approach (Larry Peterson e Bruce Davie).

### Resultado esperado

Explicar o que acontece na rede quando uma aplicação web é acessada e implementar um cliente e um servidor com sockets.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-15.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16 — Processos de Software e Métodos Ágeis]]

## Módulo 16 — Processos de Software e Métodos Ágeis

**Depende de:** [[#Módulo 9 — Introdução à Engenharia de Software|Módulo 9]]

### Objetivo

Conhecer, comparar e adaptar processos de desenvolvimento, dos dirigidos por plano aos ágeis.

### Tópicos

- [ ] 1. Conceitos e terminologia de processos de software
- [ ] 2. Modelos de ciclo de vida: cascata, modelo V, espiral e incremental
- [ ] 3. Processo unificado
- [ ] 4. Manifesto Ágil e princípios ágeis
- [ ] 5. Scrum: papéis, eventos e artefatos
- [ ] 6. Extreme Programming (XP) e suas práticas
- [ ] 7. Kanban e desenvolvimento enxuto
- [ ] 8. Modelagem e definição de processos
- [ ] 9. Normas e modelos de processo (ISO/IEC 12207, CMMI, MPS.BR)
- [ ] 10. Medição e melhoria de processos
- [ ] 11. Adaptação do processo ao contexto do projeto

### Leituras

- Básica: Engenharia de Software (Ian Sommerville).
- Básica: Engenharia de Software: uma abordagem profissional (Roger S. Pressman e Bruce R. Maxim).
- Complementar: Desenvolvimento de Software com Scrum (Mike Cohn).
- Complementar: Programação Extrema (XP) Explicada (Kent Beck).
- Complementar: Metodologias Ágeis: engenharia de software sob medida (José Henrique Teixeira de Carvalho Sbrocco e Paulo Cesar de Macedo).
- Complementar: Introdução ao RUP: Rational Unified Process (Philippe Kruchten).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 2.
- Alternativa aberta: The Scrum Guide (Ken Schwaber e Jeff Sutherland).

### Resultado esperado

Escolher e justificar um processo para um projeto e conduzir um ciclo de Scrum ou XP.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-16.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 17 — Engenharia de Requisitos|Módulo 17 — Engenharia de Requisitos]]

## Módulo 17 — Engenharia de Requisitos

**Depende de:** [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16]]

### Objetivo

Elicitar, analisar, especificar, validar e gerenciar requisitos de software.

### Tópicos

- [ ] 1. Requisitos de produto, de projeto e restrições; fronteira do sistema
- [ ] 2. Requisitos funcionais e não funcionais
- [ ] 3. Fontes e técnicas de elicitação
- [ ] 4. Modelagem de processos de negócio
- [ ] 5. Casos de uso
- [ ] 6. Histórias de usuário e backlog do produto
- [ ] 7. Mapeamento de histórias
- [ ] 8. Especificação e documentação de requisitos
- [ ] 9. Atributos de qualidade de requisitos
- [ ] 10. Validação de requisitos e prototipação
- [ ] 11. Gerência de requisitos e rastreabilidade

### Leituras

- Básica: Engenharia de Requisitos (Sheila Reinehr).
- Básica: Engenharia de Requisitos: software orientado ao negócio (Carlos Eduardo Vazquez e Guilherme Siqueira Simões).
- Complementar: Escrevendo Casos de Uso Eficazes (Alistair Cockburn).
- Complementar: Software Requirements (Karl E. Wiegers e Joy Beatty).
- Complementar: Requirements Engineering: Processes and Techniques (Gerald Kotonya e Ian Sommerville).
- Complementar: User Story Mapping (Jeff Patton e Peter Economy).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 3.

### Resultado esperado

Produzir um documento de requisitos, ou um backlog com critérios de aceitação, validado e rastreável.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-17.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 18 — Análise e Projeto Orientados a Objetos|Módulo 18 — Análise e Projeto Orientados a Objetos]]

## Módulo 18 — Análise e Projeto Orientados a Objetos

**Depende de:** [[#Módulo 7 — Programação Orientada a Objetos|Módulo 7]], [[#Módulo 17 — Engenharia de Requisitos|Módulo 17]]

### Objetivo

Transformar requisitos em modelos orientados a objetos com UML.

### Tópicos

- [ ] 1. Do requisito ao modelo: análise orientada a objetos
- [ ] 2. Modelo de domínio e diagrama de classes conceitual
- [ ] 3. Diagramas de casos de uso
- [ ] 4. Diagramas de sequência e de comunicação
- [ ] 5. Diagramas de estados e de atividades
- [ ] 6. Contratos de operação
- [ ] 7. Atribuição de responsabilidades com padrões GRASP
- [ ] 8. Diagrama de classes de projeto
- [ ] 9. Diagramas de pacotes, componentes e implantação
- [ ] 10. Desenvolvimento iterativo e ferramentas CASE

### Leituras

- Básica: Utilizando UML e Padrões (Craig Larman).
- Básica: UML Essencial (Martin Fowler).
- Complementar: UML: Guia do Usuário (Grady Booch, James Rumbaugh e Ivar Jacobson).
- Complementar: Princípios de Análise e Projeto de Sistemas com UML (Eduardo Bezerra).
- Complementar: Análise e Design Orientados a Objetos para Sistemas de Informação (Raul Sidnei Wazlawick).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 4.

### Resultado esperado

Modelar um sistema de médio porte em UML, da análise ao projeto de classes, justificando a distribuição de responsabilidades.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-18.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 19 — Projeto de Software e Padrões de Projeto|Módulo 19 — Projeto de Software e Padrões de Projeto]]

## Módulo 19 — Projeto de Software e Padrões de Projeto

**Depende de:** [[#Módulo 18 — Análise e Projeto Orientados a Objetos|Módulo 18]]

### Objetivo

Aplicar princípios e padrões de projeto para obter código coeso, pouco acoplado e fácil de mudar.

### Tópicos

- [ ] 1. Princípios de projeto: separação de interesses e ocultamento de informação
- [ ] 2. Coesão e acoplamento
- [ ] 3. Princípios SOLID
- [ ] 4. Projeto orientado por responsabilidades
- [ ] 5. Padrões de criação
- [ ] 6. Padrões estruturais
- [ ] 7. Padrões comportamentais
- [ ] 8. Projeto de componentes e de interfaces entre componentes
- [ ] 9. Persistência, exceções e eventos no projeto
- [ ] 10. Código limpo e convenções

### Leituras

- Básica: Padrões de Projeto: soluções reutilizáveis de software orientado a objetos (Erich Gamma, Richard Helm, Ralph Johnson e John Vlissides).
- Básica: Utilizando UML e Padrões (Craig Larman).
- Complementar: Refatoração para Padrões (Joshua Kerievsky).
- Complementar: Explicando Padrões de Projeto (Alan Shalloway e James R. Trott).
- Complementar: Código Limpo (Robert C. Martin).
- Complementar: Use a Cabeça! Padrões de Projetos (Eric Freeman, Elisabeth Freeman, Kathy Sierra e Bert Bates).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 5 e 6.

### Resultado esperado

Identificar problemas de projeto em código existente e resolvê-los aplicando princípios e padrões adequados.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-19.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 20 — Interação Humano-Computador|Módulo 20 — Interação Humano-Computador]]

## Módulo 20 — Interação Humano-Computador

**Depende de:** [[#Módulo 17 — Engenharia de Requisitos|Módulo 17]]

### Objetivo

Projetar e avaliar interfaces usáveis e acessíveis com métodos centrados no usuário.

### Tópicos

- [ ] 1. Conceitos de interação e interface humano-computador
- [ ] 2. Aspectos humanos: percepção, cognição e memória
- [ ] 3. Estilos e paradigmas de interação
- [ ] 4. Teorias de IHC: engenharia cognitiva e engenharia semiótica
- [ ] 5. Processo de design de interação centrado no usuário
- [ ] 6. Levantamento de necessidades e personas
- [ ] 7. Prototipação de baixa e alta fidelidade
- [ ] 8. Avaliação por inspeção: avaliação heurística e percurso cognitivo
- [ ] 9. Avaliação com usuários e aspectos éticos
- [ ] 10. Usabilidade e ergonomia
- [ ] 11. Acessibilidade e recomendações W3C

### Leituras

- Básica: Design de Interação: além da interação humano-computador (Yvonne Rogers, Helen Sharp e Jennifer Preece).
- Básica: Interação Humano-Computador (Simone Diniz Junqueira Barbosa e Bruno Santana da Silva).
- Complementar: Ergonomia e Usabilidade: conhecimentos, métodos e aplicações (Walter Cybis, Adriana Holtz Betiol e Richard Faust).
- Complementar: Usabilidade na Web (Jakob Nielsen e Hoa Loranger).
- Alternativa aberta: Design e Avaliação de Interfaces Humano-Computador (Heloísa Vieira da Rocha e Maria Cecília C. Baranauskas (NIED/Unicamp)).

### Resultado esperado

Prototipar uma interface a partir de requisitos e avaliá-la com inspeção e com usuários.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-20.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 21 — Teste de Software|Módulo 21 — Teste de Software]]

## Módulo 21 — Teste de Software

**Depende de:** [[#Módulo 7 — Programação Orientada a Objetos|Módulo 7]], [[#Módulo 9 — Introdução à Engenharia de Software|Módulo 9]]

### Objetivo

Planejar e executar verificação e validação, e projetar casos de teste com técnicas sistemáticas.

### Tópicos

- [ ] 1. Conceitos de verificação, validação, defeito, erro e falha
- [ ] 2. Revisões e inspeções de software
- [ ] 3. Níveis de teste: unidade, integração, sistema e aceitação
- [ ] 4. Teste funcional (caixa-preta): partição e valor-limite
- [ ] 5. Teste estrutural (caixa-branca) e critérios de cobertura
- [ ] 6. Teste baseado em defeitos e teste de mutação
- [ ] 7. Casos de teste a partir de casos de uso e histórias de usuário
- [ ] 8. Testes de unidade automatizados e objetos dublês (mocks)
- [ ] 9. Desenvolvimento guiado por testes (TDD)
- [ ] 10. Teste de regressão e integração com ferramentas de integração contínua
- [ ] 11. Planejamento e documentação de testes

### Leituras

- Básica: Introdução ao Teste de Software (Márcio Delamaro, José Carlos Maldonado e Mario Jino).
- Básica: The Art of Software Testing (Glenford J. Myers, Corey Sandler e Tom Badgett).
- Complementar: TDD: Desenvolvimento Guiado por Testes (Kent Beck).
- Complementar: Teste e Análise de Software: processos, princípios e técnicas (Mauro Pezzè e Michal Young).
- Complementar: xUnit Test Patterns (Gerard Meszaros).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 8.

### Resultado esperado

Projetar e automatizar uma suíte de testes com critérios de cobertura definidos e aplicar TDD em uma funcionalidade nova.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-21.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 22 — Arquitetura de Software|Módulo 22 — Arquitetura de Software]]

## Módulo 22 — Arquitetura de Software

**Depende de:** [[#Módulo 19 — Projeto de Software e Padrões de Projeto|Módulo 19]]

### Objetivo

Definir, avaliar e documentar a arquitetura de um sistema em função dos atributos de qualidade.

### Tópicos

- [ ] 1. Definição de arquitetura e seu impacto no projeto
- [ ] 2. Atributos de qualidade e cenários
- [ ] 3. Táticas arquiteturais
- [ ] 4. Estilos: camadas, cliente-servidor, pipes and filters
- [ ] 5. Estilos orientados a eventos e publish-subscribe
- [ ] 6. MVC e arquiteturas para aplicações corporativas
- [ ] 7. Arquitetura orientada a serviços e microsserviços
- [ ] 8. Visões e notações arquiteturais
- [ ] 9. Rastreabilidade entre requisitos e arquitetura
- [ ] 10. Linhas de produtos e reúso em nível arquitetural
- [ ] 11. Avaliação de arquitetura e trade-offs

### Leituras

- Básica: Software Architecture in Practice (Len Bass, Paul Clements e Rick Kazman).
- Básica: Padrões de Arquitetura de Aplicações Corporativas (Martin Fowler).
- Complementar: Arquitetura Limpa (Robert C. Martin).
- Complementar: Documenting Software Architectures: Views and Beyond (Paul Clements e outros).
- Complementar: Pattern-Oriented Software Architecture, vol. 1 (Frank Buschmann e outros).
- Complementar: Essential Software Architecture (Ian Gorton).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 7.

### Resultado esperado

Propor e documentar, em visões, a arquitetura de um sistema e justificar os trade-offs entre atributos de qualidade.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-22.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 23 — Gerência de Configuração e DevOps|Módulo 23 — Gerência de Configuração e DevOps]]

## Módulo 23 — Gerência de Configuração e DevOps

**Depende de:** [[#Módulo 21 — Teste de Software|Módulo 21]]

### Objetivo

Controlar versões, mudanças e entregas, automatizando integração e implantação.

### Tópicos

- [ ] 1. Conceitos e terminologia de gerência de configuração
- [ ] 2. Identificação de itens de configuração e linhas de base
- [ ] 3. Controle de versões distribuído com Git
- [ ] 4. Estratégias de ramificação e integração
- [ ] 5. Controle de mudanças e relatórios de status
- [ ] 6. Normas e modelos (IEEE 828, MPS.BR) aplicados à gerência de configuração
- [ ] 7. Integração contínua
- [ ] 8. Entrega e implantação contínuas
- [ ] 9. Infraestrutura como código e contêineres
- [ ] 10. Cultura e práticas DevOps
- [ ] 11. Monitoramento e observabilidade

### Leituras

- Básica: Entrega Contínua (Jez Humble e David Farley).
- Básica: Configuration Management: Principles and Practice (Anne Mette Jonassen Hass).
- Complementar: Gerência de Configuração: técnicas e práticas no desenvolvimento do software (Leonardo Molinari).
- Complementar: Manual de DevOps (Gene Kim, Jez Humble, Patrick Debois e John Willis).
- Complementar: Software Configuration Management Patterns (Stephen P. Berczuk e Brad Appleton).
- Alternativa aberta: Pro Git (Scott Chacon e Ben Straub).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 10.

### Resultado esperado

Montar um repositório com fluxo de ramificação definido e um pipeline que compila, testa e implanta automaticamente.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-23.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 24 — Qualidade e Medição de Software|Módulo 24 — Qualidade e Medição de Software]]

## Módulo 24 — Qualidade e Medição de Software

**Depende de:** [[#Módulo 5 — Probabilidade e Estatística|Módulo 5]], [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16]], [[#Módulo 21 — Teste de Software|Módulo 21]]

### Objetivo

Garantir e medir a qualidade do produto e do processo de software.

### Tópicos

- [ ] 1. Conceitos de qualidade de produto e de processo
- [ ] 2. Modelos de qualidade de produto (ISO/IEC 25000)
- [ ] 3. Garantia da qualidade e revisões
- [ ] 4. Métricas de produto, processo e projeto
- [ ] 5. Medição orientada a objetivos (GQM) e ISO/IEC 15939
- [ ] 6. Coleta, análise e controle estatístico de medidas
- [ ] 7. Modelos de maturidade: CMMI e MPS.BR
- [ ] 8. Melhoria de processos de software
- [ ] 9. Análise estática de código e dívida técnica
- [ ] 10. Custo e retorno da qualidade

### Leituras

- Básica: Qualidade de Software: aprenda as metodologias e técnicas mais modernas para o desenvolvimento de software (André Koscianski e Michel dos Santos Soares).
- Básica: Qualidade de Software (Aline Zanin e outros).
- Complementar: Software Metrics: A Rigorous and Practical Approach (Norman Fenton e Shari Lawrence Pfleeger).
- Complementar: Metrics and Models in Software Quality Engineering (Stephen H. Kan).
- Complementar: Engenharia de Software: teoria e prática (Shari Lawrence Pfleeger).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Definir um plano de medição ligado a objetivos e avaliar um produto ou processo segundo um modelo de qualidade.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-24.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 25 — Manutenção e Evolução de Software|Módulo 25 — Manutenção e Evolução de Software]]

## Módulo 25 — Manutenção e Evolução de Software

**Depende de:** [[#Módulo 19 — Projeto de Software e Padrões de Projeto|Módulo 19]], [[#Módulo 23 — Gerência de Configuração e DevOps|Módulo 23]]

### Objetivo

Compreender, modificar e evoluir sistemas existentes com segurança.

### Tópicos

- [ ] 1. Tipos de manutenção: corretiva, adaptativa, perfectiva e preventiva
- [ ] 2. Leis de evolução de software
- [ ] 3. Questões técnicas e gerenciais da manutenção
- [ ] 4. Estimativa de custo de manutenção
- [ ] 5. Compreensão de programas
- [ ] 6. Refatoração e catálogo de refatorações
- [ ] 7. Code smells
- [ ] 8. Engenharia reversa e reengenharia
- [ ] 9. Migração e modernização de sistemas legados
- [ ] 10. Processos de manutenção (IEEE 14764)

### Leituras

- Básica: Refatoração: aperfeiçoando o projeto de código existente (Martin Fowler).
- Básica: Software Maintenance: Concepts and Practice (Penny Grubb e Armstrong A. Takang).
- Complementar: Code Complete (Steve McConnell).
- Complementar: Evolving Software Systems (Tom Mens, Alexander Serebrenik e Anthony Cleve).
- Alternativa aberta: Object-Oriented Reengineering Patterns (Serge Demeyer, Stéphane Ducasse e Oscar Nierstrasz).
- Alternativa aberta: Engenharia de Software Moderna (Marco Tulio Valente) — cap. 9.

### Resultado esperado

Refatorar um sistema legado com testes de proteção e planejar sua evolução.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-25.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 26 — Desenvolvimento Web|Módulo 26 — Desenvolvimento Web]]

## Módulo 26 — Desenvolvimento Web

**Depende de:** [[#Módulo 13 — Banco de Dados|Módulo 13]], [[#Módulo 15 — Redes de Computadores|Módulo 15]], [[#Módulo 19 — Projeto de Software e Padrões de Projeto|Módulo 19]], [[#Módulo 20 — Interação Humano-Computador|Módulo 20]]

### Objetivo

Construir aplicações web completas, do front-end ao back-end com persistência.

### Tópicos

- [ ] 1. Arquitetura cliente-servidor e protocolo HTTP
- [ ] 2. HTML e semântica de documentos
- [ ] 3. CSS e design responsivo
- [ ] 4. JavaScript e manipulação do DOM
- [ ] 5. Frameworks de front-end
- [ ] 6. Programação do lado do servidor
- [ ] 7. APIs REST e JSON
- [ ] 8. Padrão MVC e camada de acesso a dados
- [ ] 9. Sessões, cookies e autenticação
- [ ] 10. Acessibilidade e usabilidade na web
- [ ] 11. Noções de segurança de aplicações web

### Leituras

- Básica: JavaScript: O Guia Definitivo (David Flanagan).
- Básica: Engenharia Web (Roger S. Pressman e David Lowe).
- Complementar: HTML5: a linguagem de marcação que revolucionou a web (Maurício Samy Silva).
- Complementar: JSON Básico (Ben Smith).
- Complementar: Desenvolvimento de Software II: introdução ao desenvolvimento web com HTML, CSS, JavaScript e PHP (Evandro Manara Miletto e Silvia de Castro Bertagnolli).
- Complementar: Java para Web: desenvolvimento de aplicações (William Pereira Alves).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Desenvolver e implantar uma aplicação web com front-end, API REST e banco de dados.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-26.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 27 — Desenvolvimento para Dispositivos Móveis|Módulo 27 — Desenvolvimento para Dispositivos Móveis]]

## Módulo 27 — Desenvolvimento para Dispositivos Móveis

**Depende de:** [[#Módulo 26 — Desenvolvimento Web|Módulo 26]]

### Objetivo

Projetar e implementar aplicativos móveis considerando as restrições e recursos dos dispositivos.

### Tópicos

- [ ] 1. Características e restrições dos dispositivos móveis
- [ ] 2. Plataformas e ambientes de desenvolvimento
- [ ] 3. Arquitetura de aplicativos móveis
- [ ] 4. Ciclo de vida de telas (activities) e navegação
- [ ] 5. Interfaces e layouts
- [ ] 6. Persistência local de dados
- [ ] 7. Comunicação com serviços web
- [ ] 8. Serviços e tarefas em segundo plano
- [ ] 9. Sensores, localização e mapas
- [ ] 10. Sensibilidade ao contexto
- [ ] 11. Testes e publicação de aplicativos

### Leituras

- Básica: Android para Programadores: uma abordagem baseada em aplicativos (Paul Deitel, Harvey Deitel e coautores).
- Básica: Desenvolvimento para Dispositivos Móveis (Diego Bittencourt de Oliveira e outros).
- Complementar: Google Android: aprenda a criar aplicações para dispositivos móveis com o Android SDK (Ricardo R. Lecheta).
- Complementar: Writing Mobile Code: Essential Software Engineering for Building Mobile Applications (Ivo Salmre).
- Complementar: Use a Cabeça! Desenvolvendo para Android (Dawn Griffiths e David Griffiths).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Publicar um aplicativo móvel que consome uma API, persiste dados localmente e usa ao menos um sensor.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-27.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 28 — Sistemas Distribuídos|Módulo 28 — Sistemas Distribuídos]]

## Módulo 28 — Sistemas Distribuídos

**Depende de:** [[#Módulo 15 — Redes de Computadores|Módulo 15]], [[#Módulo 22 — Arquitetura de Software|Módulo 22]]

### Objetivo

Entender os princípios de sistemas distribuídos e de computação em nuvem e aplicá-los no projeto de software.

### Tópicos

- [ ] 1. Características e desafios dos sistemas distribuídos
- [ ] 2. Arquiteturas de sistemas distribuídos
- [ ] 3. Processos, threads e virtualização
- [ ] 4. Comunicação: RPC, mensagens e fluxos
- [ ] 5. Nomeação
- [ ] 6. Sincronização e relógios lógicos
- [ ] 7. Consistência e replicação
- [ ] 8. Tolerância a falhas
- [ ] 9. Segurança em sistemas distribuídos
- [ ] 10. Computação em nuvem e contêineres
- [ ] 11. Noções de programação paralela

### Leituras

- Básica: Sistemas Distribuídos: conceitos e projeto (George Coulouris, Jean Dollimore e Tim Kindberg).
- Básica: Sistemas Distribuídos: princípios e paradigmas (Andrew S. Tanenbaum e Maarten van Steen).
- Complementar: Construindo Software como Serviço (SaaS): uma abordagem ágil usando computação em nuvem (Armando Fox e David Patterson).
- Alternativa aberta: Distributed Systems (Maarten van Steen e Andrew S. Tanenbaum).

### Resultado esperado

Projetar um serviço distribuído tratando comunicação, replicação e falhas parciais.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-28.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 29 — Gerência de Projetos de Software|Módulo 29 — Gerência de Projetos de Software]]

## Módulo 29 — Gerência de Projetos de Software

**Depende de:** [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16]]

### Objetivo

Planejar, estimar, acompanhar e controlar projetos de software, com abordagens tradicionais e ágeis.

### Tópicos

- [ ] 1. Conceitos, ciclo de vida do projeto e partes interessadas
- [ ] 2. Estruturas organizacionais e seleção de projetos
- [ ] 3. Gerenciamento de escopo
- [ ] 4. Estimativas de tamanho e esforço (pontos de função, pontos de história)
- [ ] 5. Gerenciamento de tempo e cronograma
- [ ] 6. Gerenciamento de custos
- [ ] 7. Gerenciamento de riscos
- [ ] 8. Gerenciamento de equipes e comunicação
- [ ] 9. Gerenciamento de qualidade e aquisições
- [ ] 10. Gestão ágil de projetos com Scrum
- [ ] 11. Acompanhamento e controle; ferramentas de apoio

### Leituras

- Básica: Um Guia do Conhecimento em Gerenciamento de Projetos (Guia PMBOK) (Project Management Institute).
- Básica: Gestão Ágil de Projetos (Robson Camargo e Thomaz Ribas).
- Complementar: Scrum Essencial: um guia prático para o mais popular processo ágil (Kenneth S. Rubin).
- Complementar: Gerenciamento de Projetos: estabelecendo diferenciais competitivos (Ricardo Viana Vargas).
- Complementar: Análise de Pontos de Função: medição, estimativas e gerenciamento de projetos de software (Carlos Eduardo Vazquez, Guilherme Siqueira Simões e Renato Machado Albert).
- Complementar: Scrum em Ação: gerenciamento de desenvolvimento ágil de projetos de software (Andrew Pham e Phuong-Van Pham).
- Alternativa aberta: The Scrum Guide (Ken Schwaber e Jeff Sutherland).

### Resultado esperado

Elaborar um plano de projeto com escopo, estimativas, cronograma e riscos, e acompanhá-lo com práticas ágeis.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-29.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 30 — Engenharia de Software Experimental|Módulo 30 — Engenharia de Software Experimental]]

## Módulo 30 — Engenharia de Software Experimental

**Depende de:** [[#Módulo 5 — Probabilidade e Estatística|Módulo 5]], [[#Módulo 16 — Processos de Software e Métodos Ágeis|Módulo 16]]

### Objetivo

Avaliar práticas e ferramentas de engenharia de software com método científico.

### Tópicos

- [ ] 1. Método científico e pesquisa em computação
- [ ] 2. Tipos de estudo: experimento, estudo de caso e survey
- [ ] 3. Métodos quantitativos e qualitativos
- [ ] 4. Formulação de hipóteses e variáveis
- [ ] 5. Planejamento de experimentos controlados
- [ ] 6. Ameaças à validade
- [ ] 7. Análise estatística dos resultados
- [ ] 8. Estudos secundários: revisão e mapeamento sistemáticos
- [ ] 9. Síntese de evidências
- [ ] 10. Ética em pesquisa e relato de estudos

### Leituras

- Básica: Metodologia de Pesquisa para Ciência da Computação (Raul Sidnei Wazlawick).
- Básica: Experimentation in Software Engineering: An Introduction (Claes Wohlin e outros).
- Complementar: Basics of Software Engineering Experimentation (Natalia Juristo e Ana M. Moreno).
- Complementar: Evidence-Based Software Engineering and Systematic Reviews (Barbara Kitchenham, David Budgen e Pearl Brereton).
- Complementar: Estudo de Caso: planejamento e métodos (Robert K. Yin).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Planejar, executar e relatar um estudo empírico pequeno, discutindo suas ameaças à validade.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-30.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 31 — Inteligência Artificial|Módulo 31 — Inteligência Artificial]]

## Módulo 31 — Inteligência Artificial

**Depende de:** [[#Módulo 4 — Álgebra Linear|Módulo 4]], [[#Módulo 5 — Probabilidade e Estatística|Módulo 5]], [[#Módulo 11 — Projeto e Análise de Algoritmos|Módulo 11]]

### Objetivo

Conhecer as principais técnicas de IA e de aprendizado de máquina e os cuidados ao integrá-las a sistemas de software.

### Tópicos

- [ ] 1. História e caracterização dos problemas de IA
- [ ] 2. Agentes inteligentes
- [ ] 3. Busca cega e busca informada
- [ ] 4. Busca com adversários: minimax e poda alfa-beta
- [ ] 5. Representação de conhecimento e raciocínio
- [ ] 6. Aprendizado de máquina: tipos e paradigmas
- [ ] 7. Árvores de decisão e regras de classificação
- [ ] 8. Técnicas estatísticas de aprendizado e agrupamento
- [ ] 9. Redes neurais
- [ ] 10. Avaliação de modelos
- [ ] 11. Aplicações e implicações éticas da IA

### Leituras

- Básica: Inteligência Artificial (Stuart Russell e Peter Norvig).
- Básica: Inteligência Artificial: uma abordagem de aprendizado de máquina (Katti Faceli e outros).
- Complementar: Redes Neurais: princípios e prática (Simon Haykin).
- Complementar: Machine Learning (Tom M. Mitchell).
- Complementar: Mãos à Obra: Aprendizado de Máquina com Scikit-Learn, Keras & TensorFlow (Aurélien Géron).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Resolver um problema com busca e outro com aprendizado de máquina, avaliando o modelo com métricas adequadas.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-31.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 32 — Computação, Ética e Sociedade|Módulo 32 — Computação, Ética e Sociedade]]

## Módulo 32 — Computação, Ética e Sociedade

**Depende de:** [[#Módulo 9 — Introdução à Engenharia de Software|Módulo 9]]

### Objetivo

Refletir sobre os impactos sociais, éticos e legais da computação e sobre a responsabilidade do profissional.

### Tópicos

- [ ] 1. Fundamentos de ética e ética profissional
- [ ] 2. Códigos de ética da profissão
- [ ] 3. Propriedade intelectual e licenças de software
- [ ] 4. Privacidade e proteção de dados pessoais
- [ ] 5. Segurança, acesso não autorizado e crimes informáticos
- [ ] 6. Noções do sistema jurídico brasileiro e direito digital
- [ ] 7. Responsabilidade civil e penal no desenvolvimento de software
- [ ] 8. Mercado de trabalho e diversidade na computação
- [ ] 9. Acessibilidade, inclusão e direitos humanos
- [ ] 10. Sustentabilidade e impacto ambiental do software
- [ ] 11. Ética em inteligência artificial

### Leituras

- Básica: Ética em Computação (Paulo Cesar Masiero).
- Básica: Ética Profissional (Antônio Lopes de Sá).
- Complementar: Ética na Computação: uma abordagem baseada em casos (Robert N. Barger).
- Complementar: Direito Digital (Patrícia Peck Pinheiro).
- Complementar: Ethics for the Information Age (Michael J. Quinn).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Analisar um caso real à luz de códigos de ética e da legislação, propondo uma conduta fundamentada.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-32.md` (modelo em `_templates/anotacao.md`).

Próximo: [[#Módulo 33 — Empreendedorismo e Inovação|Módulo 33 — Empreendedorismo e Inovação]]

## Módulo 33 — Empreendedorismo e Inovação

**Depende de:** [[#Módulo 29 — Gerência de Projetos de Software|Módulo 29]]

### Objetivo

Identificar oportunidades e transformar ideias de software em negócios ou projetos inovadores.

### Tópicos

- [ ] 1. Conceito de empreendedorismo e perfil empreendedor
- [ ] 2. Ideias, oportunidades e criatividade
- [ ] 3. Inovação e seus tipos
- [ ] 4. Modelagem de negócios com o Canvas
- [ ] 5. Startups e validação de hipóteses de negócio
- [ ] 6. Plano de negócios
- [ ] 7. Propriedade intelectual e transferência de tecnologia
- [ ] 8. Incubadoras, parques tecnológicos e fontes de financiamento
- [ ] 9. Transformação digital
- [ ] 10. Noções de marketing digital

### Leituras

- Básica: Empreendedorismo (Robert D. Hisrich, Michael P. Peters e Dean A. Shepherd).
- Básica: Inovação e Empreendedorismo (John Bessant e Joe Tidd).
- Complementar: Empreendedorismo: transformando ideias em negócios (José Dornelas).
- Complementar: Gestão da Inovação (Joe Tidd e John Bessant).
- Complementar: Business Model Generation (Alexander Osterwalder e Yves Pigneur).
- Alternativa aberta: nenhuma verificada nas fontes consultadas.

### Resultado esperado

Elaborar e validar o modelo de negócio de um produto de software.

### Anotações

Anote em `pessoal/engenharias/engenharia-de-software/modulo-33.md` (modelo em `_templates/anotacao.md`).

## Conclusão

O percurso está concluído quando todos os tópicos dos 33 módulos estiverem marcados e você
conseguir cumprir o "Resultado esperado" de cada um. Como prova final, recomenda-se
desenvolver um sistema completo, do levantamento de requisitos à implantação automatizada,
aplicando o que foi estudado em requisitos, projeto, arquitetura, testes e DevOps.
