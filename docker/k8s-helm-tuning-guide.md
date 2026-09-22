# RAGFlow Production Kubernetes Helm Tuning & Resource Allocation

## 1. Production Sizing Guide
For enterprise multi-tenant deployments processing >100 QPS OCR, parsing, and vector retrieval:

### Resource Recommendations
- **Embedding / Infinity Workers**: 4 CPU, 8GiB RAM + NVIDIA T4/L4
- **Elasticsearch / Infinity Indexers**: NVMe SSD, minimum 16GiB RAM, heap size set to 50%
- **Task Executors**: Horizontal scaling managed by KEDA based on Redis queue depth
