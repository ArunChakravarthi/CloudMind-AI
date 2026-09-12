AI SRE / Platform Engineer — an AI-driven operational assistant that investigates live Azure/AKS incidents through read-only MCP tools, retrieves relevant engineering knowledge through Azure AI Search/RAG, correlates evidence, identifies probable root causes, and provides human-approved remediation guidance.

                         Engineer
                            │
                            ▼
                    ┌───────────────┐
                    │   FastAPI     │
                    │  Backend/API  │
                    └───────┬───────┘
                            │
                            ▼
                   ┌─────────────────┐
                   │   AI Agent /    │
                   │  Orchestrator   │
                   └───────┬─────────┘
                           │
                ┌──────────┴──────────┐
                │                     │
                ▼                     ▼
        ┌──────────────┐      ┌───────────────┐
        │  AKS MCP     │      │ Azure AI      │
        │  READ ONLY   │      │ Search / RAG  │
        └──────┬───────┘      └───────┬───────┘
               │                      │
               ▼                      ▼
              AKS                Runbooks
               │                 Postmortems
        ┌──────┼──────┐          Wiki
        ▼      ▼      ▼
       Pods  Events  Logs
                │
                └──────────┬───────────┘
                           ▼
                    Correlation Engine
                           │
                           ▼
                     Root Cause
                           │
                           ▼
                    Safe Remediation
                           │
                           ▼
                       Engineer


| Layer                | Technology                         |
| -------------------- | ---------------------------------- |
| API                  | **FastAPI**                        |
| API validation       | **Pydantic**                       |
| AI Agent             | Azure/OpenAI model + orchestration |
| Infrastructure tools | **MCP**                            |
| Kubernetes           | **AKS**                            |
| Knowledge/RAG        | **Azure AI Search**                |
| Identity             | **Microsoft Entra ID**             |
| Authorization        | **Azure RBAC + Kubernetes RBAC**   |
| Secrets              | **Azure Key Vault**                |
| Infrastructure       | **Terraform**                      |
| Observability        | **Azure Monitor / Log Analytics**  |
| Metrics              | Prometheus                         |
| Dashboard            | Grafana                            |
| Containers           | Docker                             |
| CI/CD                | Azure DevOps/GitHub Actions        |
| Security             | Zero Trust                         |
| Testing              | pytest + incident scenarios        |



          ┌───────────────────────────────┐
          │          ZERO TRUST           │
          │                               │
          │ Entra ID                      │
          │ Least Privilege               │
          │ RBAC                          │
          │ Read-only MCP                 │
          │ Secret Redaction              │
          │ PII Protection                │
          │ Input Validation              │
          │ Output Validation             │
          │ Audit Logging                 │
          │ Tool Allowlisting             │
          │ Human Approval                │
          │                               │
          └───────────────────────────────┘