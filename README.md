**智能健康档案问答系统 (RAG)**
基于 FastAPI 与 LangChain 构建的健康档案智能问答系统，结合 RAG（检索增强生成）与重排序（Re-Ranker）技术，提供精准、可解释的健康信息查询服务。

主要特性
文档预处理流水线：支持多种格式文档（PDF、TXT、Markdown 等）的加载、智能切分、向量化，并存入向量数据库。

RAG 在线检索：用户问题向量化后检索相关文档片段，结合提示词模板生成高质量回答。

重排序优化：在初步检索结果基础上，使用跨编码器（Cross-Encoder）模型进行二次排序，显著提升答案相关性与准确性。

FastAPI 后端：提供高性能异步 API 接口，支持并发请求与健康检查。

可插拔组件：支持切换不同的 Embedding 模型、向量数据库、重排序模型，便于定制。

**技术栈**
组件	技术选型
后端框架	FastAPI + Uvicorn
LLM 与 RAG 框架	LangChain
Embedding 模型	OpenAI text-embedding-3-small / 本地模型
向量数据库	Chroma / FAISS / Pinecone
重排序模型	Cohere ReRank / BAAI/bge-reranker-base
文档处理	LangChain 文档加载器 + RecursiveCharacterTextSplitter
部署	Docker / Docker Compose
