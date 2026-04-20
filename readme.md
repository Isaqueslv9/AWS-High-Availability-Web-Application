# 🚀 AWS High Availability Web Application

Com o objetivo de fortalecer minhas bases em redes e evoluir na área de DevOps, desenvolvi este projeto na AWS aplicando na prática conceitos como VPC, balanceamento de carga, segurança e escalabilidade automática.

---

# Visão geral

Neste projeto, construí uma arquitetura web na AWS com foco em alta disponibilidade, segurança e escalabilidade.

A aplicação é acessada através de um Load Balancer, que recebe as requisições da internet e distribui o tráfego entre múltiplas instâncias EC2 em diferentes zonas de disponibilidade. Isso garante que, mesmo que uma instância falhe, a aplicação continue disponível.

As instâncias foram configuradas com um servidor web utilizando NGINX, responsável por responder às requisições recebidas.

Para controle de acesso, utilizei Security Groups seguindo o princípio de menor privilégio: apenas o Load Balancer pode se comunicar com as instâncias, enquanto o acesso direto às EC2 é bloqueado.

O Auto Scaling Group foi configurado para ajustar automaticamente a quantidade de instâncias com base na utilização de CPU, garantindo melhor uso de recursos e capacidade de lidar com variações de carga.

Além disso, utilizei Network ACLs como uma camada adicional de segurança na rede.
### Fluxo da aplicação

```
Usuário → Load Balancer → EC2 (Auto Scaling) → Resposta
```

---

# Componentes utilizados

* VPC (Virtual Private Cloud)
* Subnets públicas em múltiplas AZs
* Internet Gateway
* Route Tables
* EC2 (instâncias da aplicação)
* Load Balancer (ALB)
* Auto Scaling Group
* Security Groups
* Network ACLs (NACL)
* EBS (armazenamento)

---

# Rede

* Criação de uma VPC customizada
* Subnets distribuídas em diferentes zonas de disponibilidade
* Configuração de roteamento para acesso à internet
* Associação de subnets com Route Tables

---

# Segurança

* Security Groups configurados com princípio de menor privilégio:

  * Load Balancer acessível pela internet (HTTP/HTTPS)
  * EC2 acessível apenas pelo Load Balancer
* Uso de NACL como camada adicional de controle de tráfego

---

# Balanceamento de carga

* Application Load Balancer distribuindo requisições entre múltiplas instâncias
* Health Check para garantir que apenas instâncias saudáveis recebam tráfego

---

# Escalabilidade

* Auto Scaling Group configurado com:

  * Mínimo: 1 instância
  * Desejado: 2 instâncias
  * Máximo: 3 instâncias
* Escala automática baseada em uso de CPU (Ao chegar a 50%)
* Substituição automática de instâncias não saudáveis

---

# Armazenamento

* Uso de volumes EBS como armazenamento das instâncias EC2

---

# Testes realizados

* Acesso à aplicação via Load Balancer
* Distribuição de tráfego entre instâncias
* Simulação de falha (remoção de instância)
* Validação de recriação automática pelo Auto Scaling
* Testes de carga para ativação do scaling

---

# 📸 

<img width="1914" height="941" alt="Image" src="https://github.com/user-attachments/assets/5e279ad6-bc16-4cf4-8d1d-82ccd8b9d220" />
<img width="1916" height="936" alt="Image" src="https://github.com/user-attachments/assets/a8007a62-4efe-4202-ba1b-b19d70bf733e" />
<img width="1912" height="939" alt="Image" src="https://github.com/user-attachments/assets/68311534-e853-4eae-a854-240262144365" />
<img width="1913" height="944" alt="Image" src="https://github.com/user-attachments/assets/f71492fd-ca6b-43df-9398-b57d9f14ba30" />
<img width="1919" height="947" alt="Image" src="https://github.com/user-attachments/assets/3cc1d8ab-8f29-4640-ac5d-a1e992e48b06" />


---

