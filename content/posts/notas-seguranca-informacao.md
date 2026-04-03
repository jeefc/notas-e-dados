---
title: "Notas sobre Normas de Segurança: Conceitos Iniciais"
date: 2026-04-03T10:00:00-03:00
draft: false
description: "Um resumo direto sobre os fundamentos de Segurança da Informação, frameworks (ISO/NIST) e gestão de riscos."
tags: ["segurança", "redes", "auditoria", "estudos"]
categories: ["Estudos Técnicos"]
---

Segurança da Informação vai muito além de configurar firewalls. O objetivo central é proteger a informação — tratada como um ativo valioso da empresa — para garantir a continuidade dos negócios, muitas vezes seguindo normas estabelecidas como a ISO/IEC 27002.

Abaixo, um resumo estruturado dos conceitos iniciais que fundamentam a área de auditoria e gestão de sistemas.

---

### 1. Os Pilares da Segurança

A base da segurança da informação é conhecida pela sigla **CID**:
- **Confidencialidade:** Garantir que a informação esteja disponível apenas para entidades e pessoas autorizadas.
- **Integridade:** Assegurar que os arquivos e dados são exatos e não sofreram alterações indevidas.
- **Disponibilidade:** Garantir o acesso aos dados no tempo e momento necessários.

Além da tríade principal, a ISO 27001 define outros princípios fundamentais:
- **Autenticidade:** Garantir que a entidade que acessa o sistema é realmente quem diz ser.
- **Não repúdio (ou Irretratabilidade):** Através de logs e registros, impedir que um usuário negue a autoria de uma ação ou transação.
- **Legalidade:** Atuar em conformidade com a legislação vigente (como a LGPD no Brasil).

---

### 2. O Ciclo de Vida da Segurança (NIST)

Para lidar com incidentes e manter um ambiente seguro, o framework do NIST estabelece um ciclo lógico de cinco etapas:
`Identificação > Proteção > Detecção > Resposta > Recuperação`

---

### 3. Gestão de Riscos

Todos os ativos de uma empresa (pessoas, infraestrutura, informação) possuem riscos. A análise de risco geralmente segue a fórmula: 
**Risco = Probabilidade x Impacto (R = P * I)**. 

Essa métrica costuma ser mapeada em uma matriz de pontos (ex: <= 3 baixo, 4 a 6 médio, 8 a 9 alto, e 12 risco extremo). 

O tratamento desses riscos pode ocorrer de quatro formas:
1. **Mitigação (ou Redução):** Implementação de controles para diminuir o risco.
2. **Aceitação:** Quando o risco é classificado como baixo, a empresa o aceita, mas mantém o monitoramento constante.
3. **Eliminação:** Alterar processos ou evitar o ativo para eliminar a fonte do risco.
4. **Transferência:** Repassar a gestão do risco para terceiros (ex: contratação de seguros ou serviços especializados).

*(Nota: Mesmo após o tratamento, existem os "riscos residuais", que permanecem após a aplicação dos controles, além dos novos riscos "emergentes" que surgem com a evolução tecnológica).*

---

### 4. Controles de Segurança

Os controles são aplicados para atingir fins específicos (Prevenção, Detecção ou Resposta) e se dividem em quatro categorias principais:
- **Físicos:** Câmeras de segurança, catracas.
- **Tecnológicos (Lógicos):** Biometria, firewalls, IDS/IPS.
- **Processuais:** Políticas internas e normas da empresa.
- **Regulatórios:** Adequação às leis de proteção de dados.

---

### 5. Redes e Ameaças Comuns

As redes são a principal origem de ataques contra infraestruturas. Portas abertas representam serviços disponíveis que podem ser alvos. Alguns conceitos e vetores comuns incluem:

- **Nmap:** Ferramenta de scan de serviços de rede, utilizada tanto para manutenção/auditoria quanto para mapear vulnerabilidades.
- **Sniffing:** Captura de pacotes na rede (ex: utilizando Wireshark). A principal mitigação é o uso de protocolos criptografados e padrões mais seguros (como o IPv6 que possui IPsec integrado).
- **Ataques DoS/DDoS:** Visam exaurir os recursos do sistema, comprometendo diretamente o pilar da *Disponibilidade*.
- **Spoofing e Phishing:** Spoofing falsifica credenciais ou origens para enganar sistemas, enquanto o phishing foca na engenharia social, disparando mensagens em lote de maneira genérica para capturar informações de usuários desatentos.

A proteção contra essas ameaças exige um conjunto de práticas contínuas: configuração correta de firewalls, softwares e sistemas atualizados, autenticação forte, segmentação de rede, uso de criptografia, controle de acesso (IDS/IPS), monitoramento ativo de tráfego, backups regulares e políticas de segurança bem definidas.