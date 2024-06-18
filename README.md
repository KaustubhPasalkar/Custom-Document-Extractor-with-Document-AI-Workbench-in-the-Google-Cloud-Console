## Custom Document Extractor with Document AI Workbench in the Google Cloud Console
This repository demonstrates how to create, train, and deploy a custom document extractor using Google Cloud's Document AI Workbench. The project involves setting up the environment, defining processor fields, labeling documents, training models, and deploying the trained models. Below is a detailed technical overview of each step involved:

### Project Setup:

### 1- Create a Processor: 

<img width="726" alt="DocumentAI21" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/c9496f06-1138-439c-82c7-ece02a4278da">


In the Google Cloud console, navigate to the Document AI section and create a new processor for custom document extraction. Name the processor (e.g., my-custom-document-extractor), select the nearest region, and opt for Google-managed storage and encryption.


### 2- Processor Configuration:

<img width="727" alt="DocumentAI11" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/57eb6e99-ed42-4320-843a-77f809a37d3a">

#### i. Define Processor Fields:
Specify the fields to be extracted by the processor. Create fields such as control_number, employees_social_security_number, employer_identification_number, employers_name_address_and_zip_code, federal_income_tax_withheld, social_security_tax_withheld, social_security_wages, and wages_tips_other_compensation.
#### ii. Field Attributes: 
Define attributes like Data Type (e.g., Number, Money, Address) and Occurrence (e.g., Optional multiple, Required multiple).


### 3- Document Labeling:

<img width="717" alt="DocumentAI12" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/b37d3ddf-3094-4fa5-a994-32ebab666340">

#### i. Upload Sample Document: 
Import sample documents from Cloud Storage to the labeling console.
#### ii. Annotation: 
Use tools like bounding box and select text to annotate documents. Confirm suggested labels by the foundation model, and manually label fields that are not identified automatically.

### 4- Model Training:

<img width="723" alt="DocumentAI13" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/df556ec6-0482-4948-afba-83af0dc33db4">

#### i. Build Processor Version: 
Create a processor version using the pretrained foundation model for initial extraction. Name the version (e.g., w2-foundation-model).
#### ii. Auto-Labeling with Generative AI: 
Import additional documents, split data for training and testing, and use the foundation model to auto-label documents. Verify and manually correct auto-labeled documents.

### 5- Training Custom Model-Based Processor:

<img width="723" alt="DocumentAI15" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/0209e4ec-fbdd-487b-ab05-5e7ce54c2843">

#### i. Data Requirements: 
Ensure at least 10 training and 10 test instances for each field.
#### ii. Training Setup: 
Name the processor version (e.g., w2-custom-model), and select the Model based training method. Start training, which might take several hours.

### 6- Deployment:
#### i. Deploy Processor Version: 
Deploy the trained processor version. Set it as the Default version or use the version ID for document processing.

### 7- Evaluation and Testing:

<img width="731" alt="DocumentAI14" src="https://github.com/KaustubhPasalkar/Custom-Document-Extractor-with-Document-AI-Workbench-in-the-Google-Cloud-Console/assets/52817783/5d4295ce-0429-4345-bc44-cafbd411e9d5">

#### i. Evaluate Processor: 
Test the processor version using new documents not involved in training. Assess performance using metrics like F1 score, precision, and recall.

### 8- Using the Processor:
#### i. Manage Processor Versions: 
Handle different processor versions similarly to other processors in Document AI.
#### ii. API Integration: 
Use Document AI API for online or batch processing. Follow code samples for sending processing requests and handling responses.

## Key Insights and Summary
### 1- Automated Document Processing: 
The custom document extractor significantly reduces manual data entry and increases accuracy by automating the extraction of structured data from unstructured documents.
### 2- Flexible Configuration: 
Users can define specific fields and attributes tailored to their document types, ensuring high relevance and precision.
### 3- Efficient Annotation: 
Leveraging foundation models and generative AI for auto-labeling streamlines the annotation process, saving time and improving labeling efficiency.
### 4- Robust Training and Evaluation: 
Training custom models with sufficient data and rigorous evaluation ensures reliable performance in diverse document processing scenarios.
### 5- Scalable Deployment: 
The solution supports scalable deployment and management of multiple processor versions, catering to evolving business needs and document types.
### 6- API Integration: 
Seamless integration with the Document AI API allows for flexible and scalable document processing in various applications and workflows.

This technical description and summary provide a comprehensive guide to building a custom document extractor, automating structured data extraction from various document types using Google Cloud's Document AI Workbench.
