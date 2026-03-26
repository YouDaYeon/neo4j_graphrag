[노션(neo4j)](https://www.notion.so/aistudio/Neo4j-32d6a768e0ee800f8cdeca78cfac4077
)

### GraphDB와 LLM으로 추천시스템 챗봇 만들기(feat. Gradio)
movie_recommend.ipynb


참고 영상
https://www.youtube.com/watch?v=dzQZvebTvKc

git > neo4j-graphrag
https://github.com/neo4j/neo4j-graphrag-python?tab=readme-ov-file

- `pip install neo4j-graphrag`
- Sandbox에서 GraphDB 불러오기
- GraphRAG 구현
    
    ```python
    from neo4j_graphrag.generation import GraphRAG
    
    rag = GraphRAG(retriever=retriever, llm=llm)
    ```
    
- Text2CypherRetriever 기반 Cypher 쿼리 생성
    
    ```python
    from neo4j_graphrag.retrievers import Text2CypherRetriever
    
    retriever = Text2CypherRetriever(
        driver=driver,
        llm=llm,  # type: ignore
        neo4j_schema=neo4j_schema,
        examples=examples,
    )
    ```
    
- Gradio로 챗봇 배포
    
    ![image.png](attachment:19634b5a-5580-4879-85bc-c2f0c124d436:image.png)

### DB 조회결과에 따라 스스로 쿼리문을 수정하는 Agent | LangGraph | Text2Cypher
text2cypher_agent.ipynb


참고 영상
https://www.youtube.com/watch?v=O93x9JvDQd0
