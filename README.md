🚀 Versão Oficial e Live: Testa a ferramenta diretamente em [unattended.wintech.pt](https://unattended.wintech.pt)

# Wintech Labs - Unattended Toolkit (XP Edition) 💿

Um gerador HTML/JS leve e poderoso para criar ficheiros `autounattend.xml` à prova de falhas para o Windows 11. Especialmente otimizado para resolver os problemas de *Loop de Boot* nas builds mais recentes (24H2 / 25H2) em ambientes de virtualização e Home Labs.

## 🚀 Funcionalidades Principais

* **Anti-Loop para Hipervisores:** Permite definir manualmente o ID do disco de destino, evitando o erro clássico onde o Windows Setup tenta formatar a drive de CD-ROM (Disco 0) em máquinas virtuais Proxmox/VMware.
* **Vacina OOBE 25H2:** Injeta comandos no registo para forçar o Setup clássico e omitir validações rigorosas de metadados, prevenindo *crashes* e *reboots* silenciosos durante a fase de instalação.
* **Supressão Total de Privacidade:** Configuração integrada com `<ProtectYourPC>3</ProtectYourPC>` para saltar automaticamente todas as perguntas de localização, diagnóstico e teclado.
* **Bypass de Hardware Automático:** Ignora TPM 2.0, Secure Boot, RAM, CPU e armazenamento mínimo.
* **Instalação Silenciosa de Software (Winget):** Injeta um script inteligente de *First Logon* que aguarda pela deteção de rede (via *ping* ao 8.8.8.8) antes de instalar silenciosamente aplicações como o Google Chrome, VLC, Notepad++ e PuTTY.
* **Sem Dependências:** Construído inteiramente num único ficheiro `index.html`. Não requer *backend*, não guarda dados do utilizador e funciona totalmente do lado do cliente (*Client-Side*).

## 💡 Como Usar

1. Aceda à ferramenta online (se alojada) ou abra o ficheiro `index.html` em qualquer browser.
2. Preencha os dados do sistema e selecione o ambiente de destino. **Nota para Laboratórios:** Se usar Proxmox com discos SCSI/SATA e CD-ROM IDE, defina o ID do Disco para `1`.
3. Clique em "Aplicar e Gerar XML".
4. Coloque o ficheiro `autounattend.xml` gerado na **raiz** da sua Pen USB de instalação do Windows ou no interior da sua imagem ISO.

## 🛠️ Tecnologias Utilizadas
* HTML5, CSS3, JavaScript Vanilla
* Tema visual inspirado no clássico Windows XP (Luna Theme).

---
**Desenvolvido por João Fernandes** | Projeto independente criado para a comunidade de SysAdmins e entusiastas de Home Labs. Visite [Wintech](https://www.wintech.pt) para mais conteúdos.
