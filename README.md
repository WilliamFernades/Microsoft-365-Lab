# Microsoft 365 Hybrid Lab

Laboratório desenvolvido para praticar a administração de um ambiente híbrido Microsoft 365 utilizando uma assinatura **Microsoft 365 Business Premium (Trial)**.

O ambiente integra um **Active Directory local** com os serviços do **Microsoft 365**, permitindo o gerenciamento de identidades, dispositivos e segurança em um cenário semelhante ao encontrado em pequenas e médias empresas.

O objetivo deste repositório é documentar toda a implementação do laboratório, as configurações realizadas e os testes executados durante os estudos.

---

## Arquitetura do ambiente

```text
                         Internet
                              │
                  Microsoft 365 Business Premium
                              │
     ┌───────────────┬─────────┴─────────────┬───────────────┐
     │               │                       │               │
 Entra ID         Intune      Defender for Business    Exchange Online
     │               │
     └───────────────┘
             │
      Microsoft Entra Connect
             │
     Active Directory (On-Premises)
             │
      Domain Joined Devices
             │
   Hybrid Microsoft Entra Join
             │
      Intune Auto Enrollment
             │
 Microsoft Defender for Business
```

---

## Ambiente utilizado

* Microsoft 365 Business Premium (Trial)
* Active Directory Domain Services
* Microsoft Entra Connect
* Microsoft Entra ID
* Microsoft Intune
* Microsoft Defender for Business
* Exchange Online
* Windows Server
* Windows 11 Pro
* PowerShell

---

## Cenários implementados

### Identidade

* Active Directory local
* Estrutura de Organizational Units (OUs)
* Criação de usuários no Active Directory
* Criação de grupos no Active Directory
* Sincronização de usuários e grupos para o Microsoft Entra ID utilizando o Microsoft Entra Connect

### Gerenciamento de dispositivos

* Dispositivos ingressados no domínio (Domain Join)
* Hybrid Microsoft Entra Join
* Auto Enrollment no Microsoft Intune por GPO
* Gerenciamento dos dispositivos pelo Intune

### Segurança

* Onboarding de dispositivos no Microsoft Defender for Business
* Políticas de Compliance
* Configuration Profiles
* BitLocker
* Microsoft Defender Antivirus
* Microsoft Defender for Business

### Exchange Online

* Gerenciamento de caixas de correio
* Administração básica do Exchange Online

### Windows Autopilot

* Registro de dispositivos no Windows Autopilot
* Provisionamento automático de dispositivos
* Aplicação automática de políticas do Intune

---

## Fluxo dos dispositivos

### Dispositivos híbridos

1. O computador é ingressado no Active Directory.
2. O dispositivo é registrado no Microsoft Entra ID (Hybrid Join).
3. A GPO de Auto Enrollment registra automaticamente o dispositivo no Microsoft Intune.
4. O dispositivo recebe as políticas de gerenciamento.
5. O Microsoft Defender for Business realiza o onboarding do endpoint.

### Dispositivos novos

1. Registro do hardware no Windows Autopilot.
2. Provisionamento inicial do Windows.
3. Ingresso no Microsoft Entra ID.
4. Registro automático no Microsoft Intune.
5. Aplicação das políticas.
6. Onboarding no Microsoft Defender for Business.

---

## Objetivos do laboratório

* Administrar identidades híbridas
* Gerenciar dispositivos Windows
* Implementar políticas de segurança
* Automatizar o registro de dispositivos
* Praticar cenários comuns encontrados em ambientes corporativos
* Documentar todo o processo de implantação

---

## Estrutura do repositório

```text
docs/
images/
scripts/
README.md
```

---

## Próximos estudos

* Windows LAPS
* Attack Surface Reduction (ASR)
* Windows Update Rings
* Remediations
* Microsoft Graph PowerShell
* Automatização com PowerShell
* Políticas avançadas do Microsoft Defender
