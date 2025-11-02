# bootcamp-aws-final.
Template final - Cria uma instância EC2 Free Tier (t3.micro) com grupo de segurança na região Ohio
# Projeto AWS CloudFormation - FinalEC2

## Descrição
Template final - Cria uma instância EC2 **Free Tier (t3.micro)** com **grupo de segurança** na região **Ohio**.

## Informações da Pilha
- **Nome da pilha:** FinalEC2  
- **Status:** CREATE_COMPLETE ✅  
- **Stack ID:** `AWSTemplateFormatVersion: '2010-09-09'
Description: Template final - Cria uma instância EC2 Free Tier com grupo de segurança na região Ohio

Resources:
  MeuSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: Security group basico para EC2
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0

  MinhaInstanciaEC2:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-051f8a213df8bc089
      KeyName: minha-chave-pessoal
      SecurityGroups:
        - !Ref MeuSecurityGroup
      UserData:
        Fn::Base64: |
          #!/bin/bash
          sudo yum update -y
          sudo yum install -y httpd
          sudo systemctl start httpd
          sudo systemctl enable httpd
          echo "<h1>Servidor Web Ativo! 🚀</h1>" > /var/www/html/index.htmlarn:aws:cloudformation:us-east-1:661727108851:stack/FinalEC2/168f5360-b833-11f0-815e-0e4560fbb15f`

## Template

## Print da Pilha 
![image](https://github.com/user-attachments/assets/45b09a59-9749-4abf-bb2b-d5e54352bdbe)

