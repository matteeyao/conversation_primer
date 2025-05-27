# Diffusion Generator for T-shirt Graphic Designs

## Best Generated / Representative image from Diffusion Model

> **Learnings**: I could not get actual graphical designs to be generated from that tattoo dataset. The image dataset did not contain enough images (currently at ~4.24K images) and varied considerably from image to image in terms of color, design, shapes, etc.

The proposal for my Text Generation project is as follows:

```
1. Title
ConvoBot: An AI-Powered Conversation Starter Generator
2. Text Data Source
Dataset: Langame/conversation-starters from Hugging Face (17,470 conversation prompts)
Nature of the Problem:
This dataset contains conversation starters categorized by topics (video games, science, relationships, philosophy, etc.) with varying complexity levels from ice breakers to deep philosophical discussions. The challenge is to generate contextually appropriate, engaging conversation starters that match specific topics or social situations. This addresses the real-world problem of social anxiety and difficulty initiating meaningful conversations.
Data Characteristics:
	•	17,470 diverse prompts with topic tags
	•	Wide range of conversation depths (casual to profound)
	•	Multiple topic categories for targeted generation
	•	Varying prompt lengths and complexity
3. Model Architecture(s)
Primary Approach: Fine-tune a pre-trained transformer model (GPT-2 or T5)
	•	GPT-2 Medium/Large: For autoregressive generation of conversation starters
	•	T5-Base: For conditional generation based on topic inputs
```

The data from Dataset loading and exploration appears as such:

```
/usr/local/lib/python3.11/dist-packages/huggingface_hub/utils/_auth.py:94: UserWarning:
The secret `HF_TOKEN` does not exist in your Colab secrets.
To authenticate with the Hugging Face Hub, create a token in your settings tab (https://huggingface.co/settings/tokens), set it as secret in your Google Colab and restart your session.
You will be able to reuse this secret in all of your notebooks.
Please note that authentication is recommended but still optional to access public models or datasets.
  warnings.warn(
Dataset structure:
DatasetDict({
    train: Dataset({
        features: ['topics', 'prompt'],
        num_rows: 17470
    })
})

First few examples:
{'topics': [['video games'], ['science'], ['relationship'], ['personal', 'relationship', 'relationships', 'social', 'big talk', 'personal growth'], ['transhumanism', 'fun']], 'prompt': ['What was the most difficult aspect of mastering a video game?', 'What scientific or intellectual studies do you think would increase substantially if more people contributed around them?', 'What would you do if your partner disappeared?', 'Give eachother four praises and one critique', 'If a sufficiently advanced robot were to take your place in society and have children with a sufficiently advanced robot, would the children have any advantages over you?']}

Column names: ['topics', 'prompt']

Dataset size: 17470
```

Things to think about: "Interesting idea! Will the model be trained to generate similar-style starters, or context-aware responses based on an input topic? And will the training be conditioned on context like domain (gaming, dating, etc.)? Consider these two question during implementation. Looking forward to seeing your work."

Walk me through step-by-step how I would fine-tune GPT-2 on this dataset to execute core functions. I want to do this within a Google Collab notebook. We can leave out extra criteria for now. I will prompt you with "next" when ready to proceed to the next step.

## Business Goal / Case Statement

Accelerate and Innovate T-shirt Graphic Design Through AI.

## Assignment Context

**Relevant Industry and/or Business Function:** Fashion / Apparel Design / E-commerce

**Description:**

My goal is to revolutionize custom t-shirt graphic creation by developing a diffusion model trained on a curated dataset of tattoo-inspired artwork. This model will generate high-impact, stylized visuals optimized for apparel, offering a scalable and efficient alternative to traditional design workflows.

The output will serve as a continuous source of original t-shirt graphics, addressing three major pain points in the industry:

1. Accelerating design timelines by reducing design-to-market cycles from weeks to days through automated generation of unique visuals.

2. Cutting costs while scaling creativity by lowering dependency on expensive human designers and decreasing design production costs (estimated at up to 40%).

3. Enhancing brand differentiation and engagement by offering customers on-demand, AI-personalized design options, which may boost engagement, loyalty, and conversion rates.

Initially, this T-shirt Graphic Design Generator will function as a rapid ideation tool for in-house creative teams. By combining premium, dark-colored t-shirt manufacturing with uniquely stylized, AI-generated graphics, my goal is to establish a trusted fashion brand known for defining go-to night-out apparel for men.

By accelerating the discovery of both trending and original designs, the tool enables fashion brands to respond to consumer demand with greater speed and accuracy—streamlining production while strengthening market relevance.

## Quickstart

1. **Create a New Conda Environment**

```bash
conda create -n myenv python=3.10
```

2. **Activate the Environment**

```bash
conda activate myenv
```

3. **Install `pip` and `ipykernel`**

```bash
conda install pip ipykernel
```

4. **Install Requirements**

```bash
pip install -r requirements.txt
```

5. **Run the notebook**

  * In VSCode, select the kernel for your notebook:

    * Click on "Select Kernel" in the top right of the notebook

    * Choose your virtual environment
