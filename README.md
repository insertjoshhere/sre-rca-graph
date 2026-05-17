# sre-rca-graph
An autonomous on-call SRE framework that handles high-severity production alert text (from platforms like PagerDuty or Elastic Alerts) and orchestrates an investigative multi-agent graph to isolate root causes.

## Summary
sre-rca-graph is an autonomous on-call site reliability engineering framework designed to minimize Mean Time to Resolution (MTTR) during high-severity application outages. It intercepts unstructured production alert text from platforms like PagerDuty or Elastic Alerts and orchestrates a cyclic, multi-agent troubleshooting graph using LangGraph to isolate cascade failures and compile production-grade post-mortems.

## Project Goals & Technical Scope
This repository implements cutting-edge search-driven observability architectures, covering:

* LangGraph Cyclic Orchestration: State-machine architecture capable of executing, reviewing, and looping back through troubleshooting tasks based on execution feedback.

* Hybrid Search Integration (ESRE): Translating unstructured alert text into optimized vector and keyword query strings executed against Elasticsearch clusters.

* Context Reranking (Jina AI): Pipelines that feed retrieved application logs, metrics traces, and exceptions through dense cross-encoder rerankers to isolate the highest-signal context fragments.

* Temporal Failure Path Synthesis: Analytical nodes that piece together disparate log strings from multiple microservices into a unified chronological sequence of events.

## Business & Application Context
This framework is optimized for enterprise DevOps, SRE teams, and centralized cloud operations centers managing massive, distributed microservice infrastructures (such as real-time banking pipelines, e-commerce checkout funnels, or airline global distribution networks). When a core service suffers a catastrophic failure, it routinely floods the observability cluster with thousands of chaotic error logs across multiple downline microservices, leading to "alert fatigue" and slowing down human engineers trying to find the root cause. This framework intercepts the initial incident alert text, autonomously queries Elasticsearch clusters to extract timestamp-synchronized system logs, routes the data through semantic rerankers to isolate the high-signal failure signatures, and steps through a cyclic validation loop to trace the failure back to its source—producing a comprehensive markdown post-mortem trace before a human triage team can even assemble.
