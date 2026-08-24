# Day 23 – AWS Secrets Manager

## 🔐 Why Secrets Manager?

Applications need sensitive information such as:

* Database passwords
* API keys
* Access tokens
* Credentials

**Never hard-code secrets in application code or push them to GitHub.**

Instead, store them securely and let the application retrieve them when needed.

---

## 1. AWS Systems Manager Parameter Store

Used mainly for **application configuration and parameters**.

Examples:

```text
/app/prod/database-host
/app/prod/port
/app/prod/api-url
```

It also supports `SecureString` for sensitive values using AWS KMS.

**Best for:** Configuration and simple secrets.

---

## 2. AWS Secrets Manager

Built specifically for **managing sensitive secrets**.

Examples:

* Database credentials
* API keys
* OAuth tokens

### Important Features

* Secure secret storage
* Automatic secret rotation
* IAM-based access control
* Encryption using AWS KMS
* Multi-Region secret replication

**Best for:** Production applications that need proper secret management.

---

## 3. HashiCorp Vault

Vault is a **platform-independent secrets management system**.

It can work across:

```text
AWS + Azure + GCP + Kubernetes + On-Premises
```

### Important Features

* Dynamic secrets
* Secret rotation
* Fine-grained policies
* Multiple authentication methods
* Multi-cloud support

**Best for:** Complex or multi-cloud environments.

---

## ⚖️ Quick Comparison

| Feature         | Parameter Store | Secrets Manager | HashiCorp Vault  |
| --------------- | --------------- | --------------- | ---------------- |
| Main use        | Configuration   | Secrets         | Advanced secrets |
| AWS integration | ⭐⭐⭐             | ⭐⭐⭐             | ⭐⭐               |
| Secret rotation | Limited         | ✅               | ✅                |
| Dynamic secrets | ❌               | Limited         | ✅                |
| Multi-cloud     | ❌               | ❌               | ✅                |
| Complexity      | Low             | Low             | High             |

---

## 🧠 Easy Way to Remember

```text
Parameter Store
→ Application configuration

Secrets Manager
→ AWS application secrets

HashiCorp Vault
→ Advanced / multi-cloud secrets
```

### Key Takeaway

**Don't choose the tool with the most features. Choose the simplest tool that solves your problem.**

For a typical AWS application:

**Parameter Store → Configuration**

**Secrets Manager → Sensitive credentials**

**Vault → Advanced / multi-cloud secret management**
