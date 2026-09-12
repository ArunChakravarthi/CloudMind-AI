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


# AI SRE / Platform Engineer

An AI-powered SRE and Platform Engineering system for
investigating Azure Kubernetes Service incidents.

## Objective

The system combines:

- FastAPI
- AI agent/orchestration
- Model Context Protocol (MCP)
- Azure Kubernetes Service (AKS)
- Azure AI Search / RAG
- Azure infrastructure
- Observability
- Zero Trust security

## Core Workflow

Engineer
    ↓
FastAPI
    ↓
AI Agent
    ↓
MCP + RAG
    ↓
Live AKS telemetry + Internal knowledge
    ↓
Correlation
    ↓
Root Cause Analysis
    ↓
Safe remediation guidance

## Security Principle

The AI is read-only with respect to production infrastructure.

It can investigate infrastructure state but cannot
automatically modify or destroy production resources.

## Project Goal

Build and understand a production-oriented AI SRE /
Platform Engineering system from the ground up.