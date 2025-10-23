<div align="center">

# 🗣️ Meta LLM Chatbot: GPU Optimized

<p>
    An efficient, conversational AI agent built around a <strong>Meta Large Language Model (LLM)</strong>, featuring a simple, interactive interface powered by <strong>Gradio</strong>.
</p>
<img src="Screenshot 2025-10-23 154226.png" alt="Screenshot of the Gradio Chatbot Interface with input box and chat history." widt
</div>

---

## ✨ Project Highlights

This project focuses on balancing the power of a large language model with real-world **performance**.

* **Core Model:** Utilizes a **Meta LLM** (e.g., Llama 2) for advanced conversation.
* **User Interface:** Features a simple, browser-based **Gradio** interface for easy interaction (as seen above).
* **Performance:** Code is **GPU-optimized** to drastically reduce inference time from over 10 minutes to mere seconds.
* **Cleanup Logic:** Includes robust Python logic to prevent the model from repeating the user's input in its response.

---

## 🚀 Getting Started

Follow these steps to set up and run the chatbot locally.

### Prerequisites

You need **Python 3.8+** and access to a powerful **GPU** (with **CUDA** installed) for optimal speed.

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [YOUR_REPO_URL]
    cd [your-repo-name]
    ```

2.  **Install dependencies:**
    You will need `torch`, `transformers`, and `gradio`.
    ```bash
    pip install torch transformers gradio
    ```

### Running the Chatbot

The entire setup, configuration, and interface launch is contained within the Jupyter Notebook.

1.  **Launch the Notebook:**
    ```bash
    jupyter notebook Chatbot_with_Meta_Llm.ipynb
    ```

2.  **Execute Cells:** Run all cells in the notebook sequentially. The final cell will automatically launch the **Gradio interface** in your browser or within the notebook output itself, ready for you to chat.

---

## ⚡ Performance Optimization

We identified and resolved a major bottleneck where model inference was taking over 10 minutes. The fix was implemented in the core function (`chatbot_response`):

<details>
<summary><b>Click to see the optimization details</b></summary>
<br>
<p>
To achieve fast response times, two key Python changes were made:
<ul>
    <li>
        <b>GPU Transfer:</b> Explicitly ensuring the model and input tensors are on the GPU using <code>.to(device)</code>.
    </li>
    <li>
        <b>Response Limiting:</b> Adding the <code>max_new_tokens=100</code> parameter to the <code>model.generate()</code> call. This stops the LLM after it has generated a concise, useful response, eliminating wasted computation time.
    </li>
</ul>
</p>
</details>

---

## ✍️ Author

* **[Your Name / GitHub Username]** - [Your LinkedIn or Portfolio Link]
