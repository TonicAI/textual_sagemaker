# De-identifying Data and Fine-Tuning LLMs in Amazon SageMaker with Tonic Textual

This repository contains the Jupyter notebooks and sample data for the blog post: [Turn Sensitive Data into Safe AI Assets with Tonic Textual in Amazon SageMaker Unified Studio](https://textual.tonic.ai).

This project demonstrates a complete, end-to-end workflow for transforming raw, sensitive, unstructured text data into a safe, de-identified asset that can be used to fine-tune a Large Language Model (LLM) within the AWS ecosystem. By leveraging Tonic Textual and Amazon SageMaker, you can build powerful, customized AI models on your most valuable data without compromising security or compliance.

(To view the diagram, please download the repository and open the fine-tune-architecture-diagram.drawio.html file in your browser.)

## About the Notebooks

This repository includes two core notebooks that walk through the entire process:
1. 01-Deidentify-Data-with-Textual.ipynb: (Originally textual_demo_redaction-edited.ipynb)
This notebook guides you through the process of de-identifying sensitive data. You will:
    1. Install the tonic-textual SDK.
    2. Connect to the Tonic Textual API.
    3. Load a sample dataset (call_transcripts.csv) containing PII.
    4. Use Tonic Textual to redact sensitive entities like names, credit card numbers, and more.
    5. Save the de-identified data and upload it to an S3 bucket, preparing it for the next stage.

2. 02-Finetune-and-Deploy-LLM.ipynb: (Originally textual_fine_tune_demo_sagemaker.ipynb)
This notebook demonstrates how to use your newly de-identified data to create a custom LLM. You will:
    1. Use Amazon SageMaker JumpStart to select a foundation model (Llama 2).
    2. Configure and launch a fine-tuning job using the safe data stored in your S3 bucket.
    3. Deploy the fine-tuned model to a real-time SageMaker endpoint.
    4. Test the deployed model with sample prompts.
    5. Clean up the AWS resources to avoid unnecessary costs.

## Getting Started

To run these notebooks, you will need to have the following prerequisites in place.

### Prerequisites
- An AWS Account with access to Amazon SageMaker Unified Studio and Amazon S3.
- A Tonic Textual Account and API key. You can create a free account at [textual.tonic.ai/signup](https://textual.tonic.ai/signup).
- The contents of this GitHub repository cloned or downloaded.

### Setup Instructions
1. **Launch SageMaker Studio:** Log in to your AWS account and launch your Amazon SageMaker Unified Studio environment.
2. **Upload Files:** Upload the two notebooks (01-Deidentify-Data-with-Textual.ipynb, 02-Finetune-and-Deploy-LLM.ipynb) and the call_transcripts.csv dataset to your SageMaker Studio file browser.
3. **Open the First Notebook:** Start by opening 01-Deidentify-Data-with-Textual.ipynb.
4. **Configure API Key:** In the first notebook, locate the cell for initializing the Textual client and replace the placeholder with your Tonic Textual API key:
```python
# Initialize the Textual client with your API key
textual = Textual(api_key="YOUR_TONIC_TEXTUAL_API_KEY")
```
5. **Configure S3 Bucket:** In both notebooks, you will need to replace the placeholder your-s3-bucket-name with the name of an S3 bucket you have access to.

You are now ready to run the cells in the notebooks sequentially.

## Accompanying Blog Post
For a detailed walkthrough with full explanations of each step, business context, and screenshots, please read our complete guide:
[Turn Sensitive Data into Safe AI Assets with Tonic Textual in Amazon SageMaker Unified Studio](https://tonic.ai/textual)

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
