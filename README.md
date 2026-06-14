import streamlit as st
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

st.set_page_config(
    page_title="Personalized News Summarization System",
    layout="wide"
)

st.title("📰 Personalized News Summarization System")

# Sidebar
st.sidebar.header("Configuration")

rag_option = st.sidebar.selectbox(
    "Select RAG Technique",
    ["Dense", "Hybrid", "Fusion"]
)

llm_option = st.sidebar.selectbox(
    "Select LLM Model",
    ["GPT", "Llama", "Qwen"]
)

query = st.text_input("Enter News Query")

if st.button("Generate Summary"):

    st.success("Summary Generated Successfully")

    # Summary Section
    st.subheader("Generated Summary")
    st.write(
        "This section will display the generated summary "
        "from the selected RAG and LLM combination."
    )

    # Retrieved Documents
    st.subheader("Retrieved Documents")
    docs = pd.DataFrame({
        "Document": [
            "News Document 1",
            "News Document 2",
            "News Document 3"
        ]
    })
    st.dataframe(docs)

    # Historical Metrics
    st.subheader("Historical Metrics")

    metrics = pd.DataFrame({
        "Metric": ["ROUGE-1", "ROUGE-L", "BERTScore"],
        "Score": [0.81, 0.76, 0.89]
    })

    st.dataframe(metrics)

    # Comparison with Winner
    st.subheader("Comparison with Winner")

    comparison = pd.DataFrame({
        "Combination": [
            f"{rag_option}+{llm_option}",
            "Best Combination"
        ],
        "Score": [88, 92]
    })

    st.dataframe(comparison)

    # Ranking Chart
    st.subheader("Ranking Chart")

    ranking = pd.DataFrame({
        "Combination": [
            "Dense+GPT",
            "Dense+Llama",
            "Hybrid+GPT",
            "Hybrid+Qwen",
            "Fusion+Llama"
        ],
        "Score": [85, 82, 91, 89, 87]
    })

    fig, ax = plt.subplots(figsize=(8,4))
    ax.bar(ranking["Combination"], ranking["Score"])
    ax.set_ylabel("Score")
    ax.set_title("Combination Ranking")
    st.pyplot(fig)

    # Heatmap
    st.subheader("Heat Map")

    heatmap_df = pd.DataFrame(
        {
            "GPT": [0.85, 0.91, 0.88],
            "Llama": [0.82, 0.86, 0.87],
            "Qwen": [0.84, 0.89, 0.90]
        },
        index=["Dense", "Hybrid", "Fusion"]
    )

    fig2, ax2 = plt.subplots(figsize=(6,4))
    sns.heatmap(
        heatmap_df,
        annot=True,
        cmap="YlGnBu",
        ax=ax2
    )
    st.pyplot(fig2)

    # Best Combination
    st.subheader("🏆 Top Combination")

    st.success(
        "Best Combination: Hybrid Retrieval + GPT"
    )
