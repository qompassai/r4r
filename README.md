# The Responsible Open Science Engine: Powering Minimally Invasive AI for Mentorship
## Authors

Matt A. Porter, B.Sc<sup>1</sup>, Ariana R. Rowshan, BA<sup>2</sup>, Dawn L. Laporte, MD<sup>2</sup>, Amiethab A. Aiyer, MD<sup>2</sup>


<sup>1</sup>Qompass AI, Spokane, WA  
<sup>2</sup>The Johns Hopkins University School of Medicine, Department of Orthopaedic Surgery, Baltimore, MD

## Abstract
### Background
The rapid integration of generative artificial intelligence (genAI) into medical education has ushered in transformative changes, offering innovative tools and methodologies that enhance learning and practice. AI applications, such as adaptive learning platforms and virtual patient simulations, have become increasingly prevalent, providing personalized and immersive educational experiences. These advancements not only improve educational outcomes but also address critical needs across diverse learner populations. 

However, the swift adoption of AI technologies has highlighted significant ethical considerations, particularly concerning bias, transparency, and equitable access. In this context, our pilot study focused on harnessing genAI to enhance mentorship for aspiring orthopedic surgeons, especially those from marginalized backgrounds or institutions lacking dedicated orthopedic residencies. By developing a prototype model that delivers high-quality, personalized mentorship content, we strive to democratize access to essential resources, ensuring that all candidates have the opportunity to succeed, regardless of their circumstances.


### Methods
In response to noticeably increasing cost of AI medical education, our study focuses on the deployment of quantized, small-scale AI models on-device. This approach aims to ensure accessibility and equity, particularly for underfunded institutions and learners from non-traditional, disabled, and underepresented minority populations. We began by selecting open-source AI models renowned for their efficacy in educational contexts. To optimize these models for deployment on resource-constrained hardware, we employed quantization techniques, which reduce the precision of the model's parameters, thereby decreasing memory usage and computational demands without significantly compromising performance. Our deployment environment comprised consumer-grade Linux computers, reflecting hardware commonly available in underserved regions. We utilized standard Linux distributions, ensuring all software dependencies were met. To enhance computational efficiency, we leveraged NVIDIA's Compute Unified Device Architecture (CUDA 12.8) for on-device acceleration, enabling the models to utilize available GPU resources. The quantized models were integrated into the system in transient sandboxed enviromments as well as via hard-coded web-based application program interfaces (APIs)  to streamline deployment and ensure consistency across various infrastructures.


### Results

* Education

[Equitable Open AI Curriculum](https://github.com/qompassai/Equator)
[R3 | Open-Weight Small MultiModal Finetune of LLaMA3](https://huggingface.co/r3)

* Safety

[Safety guardrails via NIST AI Risk Management Framework ](https://github.com/qompassai/Nautilus/blob/main/RedTeam/RedAI/NIST/AI_RMF_Playbook.pdf)
[Dioptra | One NIST-endorsed tool in our purple evaluation process](https://github.com/qompassai/Nautilus/tree/main/RedTeam/RedAI/NIST/Qompass_Dioptra)
[Kyber Odyssey- Post Quantum Cryptography to secure legacy software & AI deployment](https://github.com/qompassai/KO)

* Use-Cases

[AI Data Management Protocol Walkthrough](https://www.youtube.com/watch?v=T-XGHgaJIPU&t=234s)
[Ollie | Small Multimodal Model with Web Search Tool Calling](https://www.youtube.com/watch?v=OvxrfwC3CKY&t=9s)
[Valle | SMM for MultiLingual Patient Education](https://www.youtube.com/watch?v=q-2EL-ajNKc&t=8s)


#FAQ

*Q: How would you describe AI to someone who's "not technical"?
*A: We dislike identifying people as technical or not technical. This kind language is othering and unkind. AI is like cake, not all cakes are created equal, but they can all be great in their own ways.

Yann Lecunn, Chief AI 

### AI As Cake Left-most image of poster)

The AI Layer Cake: From Foundation to Frosting
Base Layer (The Cake Foundation)
LLM Layer: Like the basic cake batter, providing fundamental reasoning and adaptability
RAG Components: Similar to adding essential ingredients like flour and eggs, enriching the base with fact-checking and knowledge retrieval
Knowledge Base: Acts as the leavening agents, helping the AI "rise" with contextual understanding and domain expertise
Middle Layers (The Filling)
Ethics & Safety Layer: Like food safety measures in baking, ensuring the "cake" is safe for consumption through:
Privacy protection (food handling standards)
Harm prevention (quality control)
Bias detection (taste testing)
Interaction Interface: Similar to the filling between cake layers:
Multi-modal support (different textures and flavors)
User input processing (mixing ingredients properly)
Personalization (custom flavor combinations)
Upper Layers (The Structure)
External Interactions: Like adding structural supports:
API integrations (binding ingredients)
Automated workflows (consistent baking processes)
Real-time decision making (temperature control)
Operational Independence: Similar to a master baker's expertise:
Self-learning (recipe refinement)
Autonomous decisions (knowing when the cake is done)
Scalability (adjusting recipe quantities)
Top Layer (The Decoration)
Governance & Auditability: Like the final decorative touches:
Transparent decision logs (recipe documentation)
Regulatory compliance (food safety certification)
Explainability (ingredient listing)
* Q: How do you mitigate against bias?

 A: "We delineate between mathematical bias (MB) - a fundamental parameter in neural network equations - and algorithmic/social bias (ASB). While MB is optimized during model training through backpropagation, ASB requires careful consideration of data sources, model architecture, and deployment strategies. We implement attention mechanisms for improved input processing and use legal open-source data and secure web-search APIs to help mitigate ASB."

 [One way to align AI against ASB](https://www.aamc.org/about-us/mission-areas/medical-education/principles-ai-use)

 ## MB at a glance

```bash
$y = w_1x_1 + w_2x_2 + ... + w_nx_n + b$

Where:
$y$ represents the model output
$(x_1, x_2, ..., x_n)$ are input features
$(w_1, w_2, ..., w_n)$ are feature weights
$b$ is the bias term
```
For neural networks, the bias term is incorporated before activation:

```bash
$ z = \sum_{i=1}^{n} w_ix_i + b $$
$ a = \sigma(z) $$

Where:
- $ z $ is the weighted sum plus bias
- $ a $ is the activation output
- $ \sigma $ is the activation function
```

The attention mechanism equation is:

```bash
$ \text{Attention}(Q,K,V) = \text{softmax}(\frac{QK^T}{\sqrt{d_k}})V $$

Where:
- $ Q $ represents Query matrix
- $ K $ represents Key matrix
- $ V $ represents Value matrix
- $ d_k $ is the dimension of the key vectors
- $ \text{softmax}(\cdot) $ normalizes scores to sum to 1
```

# How is it $0 cost?
* We self-host models and we thoughtfully implement open source software and write our own code. All hardware was already purchased prior to the grant being awarded.

# Do I have to buy a Linux computer to use this? I don't have time for that!
* No. You can run Linux and/or the tools we share alongside your existing operating system:
    * Windows users can use Windows Subsystem for Linux [WSL](https://learn.microsoft.com/en-us/windows/wsl/install)
    * Mac users can use [Homebrew](https://brew.sh/)
    * The code-base instructions were developed with both beginners and advanced users in mind.
