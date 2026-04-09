# Introduction to Amazon Bedrock

## Lesson objectives

By the end of this lesson, you will be able to do the following:

- Identify the core functionality of Amazon Bedrock.
- Identify the technical concepts required to use Amazon Bedrock.
- Identify the key features and capabilities of Amazon Bedrock.
- Identify the practical applications of Amazon Bedrock.

---

## Amazon Bedrock introduction

Amazon Bedrock is a fully managed service from Amazon Web Services (AWS) that provides access to FMs from leading AI providers through a unified API. This service empowers you to build and scale generative AI applications without needing to manage the underlying infrastructure or develop your own large language models (LLMs). With Amazon Bedrock, you can select from a variety of foundation models to find the one that best fits your specific use case requirements.

The service stands out by offering a secure environment where your data remains private. This means that your data is not used to train the models that you use. Amazon Bedrock includes capabilities for customizing foundation models with your own data through techniques like fine-tuning and Retrieval Augmented Generation (RAG). This customization helps create AI applications that better align with your organization's specific needs and knowledge domains.

Unlike other AWS machine learning services that focus on specific tasks or require extensive machine learning (ML) expertise, Amazon Bedrock provides a straightforward path to implementation. The service integrates seamlessly with other AWS services and includes built-in tools for responsible AI use, such as content filtering and model evaluation.

To learn more about using Amazon Bedrock, visit the [Amazon Bedrock documentation](https://docs.aws.amazon.com/bedrock/).

---

## Amazon Bedrock core functionality

Amazon Bedrock delivers a comprehensive platform for building generative AI applications by providing access to foundation models through a unified API. The service eliminates the need to manage complex infrastructure or negotiate separate agreements with multiple AI providers. At its core, Amazon Bedrock focuses on making powerful AI models accessible while maintaining security, customization capabilities, and operational efficiency for your applications.

### Access to AWS models

Amazon Bedrock offers a suite of foundation models developed by AWS that provide versatile AI capabilities for various applications. These models are designed to handle tasks ranging from natural language processing to code generation, to help developers build sophisticated AI-powered solutions with ease.

The foundation models provided by AWS in Amazon Bedrock are continually refined and updated to deliver state-of-the-art performance. They offer customization options for businesses to fine-tune the models for specific use cases, while maintaining the security and scalability benefits of the AWS Cloud infrastructure.

The Amazon Nova models are available in Amazon Bedrock:

- Nova Micro: A text-only model offering the lowest latency responses at very low cost, ideal for applications requiring fast processing of text inputs
- Nova Lite: A cost-effective multimodal model that rapidly processes image, video, and text inputs, suitable for interactive and high-volume applications
- Nova Pro: A highly capable multimodal model balancing accuracy, speed, and cost for a wide range of tasks, including video summarization and software development
- Nova Premier: The most advanced multimodal model for complex tasks and model distillation the enables creation of specialized versions of other Nova models
- Nova Canvas: A cost-effective image generation model that creates professional-grade images from text or image prompts, with built-in editing features and safety controls
- Nova Reel: A video generation model that creates high-quality videos from text and images, and offers control over visual style, pacing, and camera motion
- Nova Sonic: A state-of-the-art speech model that enables real-time, human-like voice conversations with low latency and support for expressive voices

In addition, the Amazon Titan family of FMs are available in Amazon Bedrock and have been trained on AWS curated datasets.

### Access to additional models

Amazon Bedrock provides access to a diverse collection of FMs from leading AI companies including Anthropic, AI21 Labs, Cohere, Meta, and Stability AI. You can experiment with these models in the Amazon Bedrock console to evaluate their capabilities before implementation. When you select a model, you can integrate it into your applications by using the Amazon Bedrock API, which standardizes the interaction regardless of the model provider.

All the infrastructure management required for model inference is managed by Amazon Bedrock. The service automatically scales to meet your application demands. This approach significantly reduces the technical barriers to implementing generative AI, because you don't need specialized knowledge about model deployment or optimization to achieve production-quality results.

### Model customization

Amazon Bedrock offers multiple approaches to customize foundation models for your specific use cases without requiring deep machine learning expertise. Through fine-tuning, you can adapt models to your organization's specific style, terminology, and domain knowledge by training them on your own examples.

For scenarios where you need models to access your proprietary information without retraining, Amazon Bedrock provides RAG capabilities. This technique enhances model responses by retrieving relevant information from your data sources and incorporating it into the generation process. The customization options ensure that the AI applications that you build reflect your organization's unique requirements and knowledge base.

## Amazon Bedrock technical concepts

---

Amazon Bedrock operates at the intersection of machine learning, cloud computing, and application development. The service abstracts much of the underlying complexity of working with foundation models, but understanding certain technical concepts remains important for effective implementation. Knowledge of these concepts helps you make informed decisions about model selection, customization approaches, and integration strategies when building generative AI applications with Amazon Bedrock.

To learn more, choose each of the numbered markers.

### Foundation models

Foundation models (FMs) are large-scale AI models trained on vast amounts of data that can be adapted to a wide range of tasks. These models serve as the building blocks for generative AI applications in Amazon Bedrock, and provide capabilities like text generation, image creation, and more.

Foundation models differ from traditional machine learning models in their versatility and scale. Rather than being trained for a single specific task, they learn general patterns from diverse data sources that can be applied across multiple domains and use cases.

FMs operate across several different modalities. The following modalities are available in Amazon Bedrock:

- Text encompasses text generation, comprehension, and processing. Text models can generate written content, answer questions, summarize information, and perform various language-based tasks.
- Image involves generating, processing, or interpreting visual content. Image models can create images from text descriptions or analyze visual information.
- Embeddings convert input (typically text) into numerical vector representations that capture semantic meaning. Embeddings are particularly useful for knowledge bases, semantic search, and understanding relationships between content.

### Tokens and token limits

Tokens are the basic units that foundation models process, and represent pieces of text like words or parts of words. When you send a prompt to a model in Amazon Bedrock, the text is divided into tokens before processing.

Each model in Amazon Bedrock has specific token limits that constrain the combined length of inputs and outputs. Understanding these limits is crucial for designing effective prompts and managing costs, because pricing is often based on token usage.

### Prompt engineering

Prompt engineering involves crafting effective instructions for foundation models to produce desired outputs. The way you structure and phrase your prompts significantly impacts the quality and relevance of the model's responses.

Effective prompt engineering requires understanding techniques like providing examples, specifying output formats, and breaking complex tasks into manageable steps. This skill becomes increasingly important as you move from basic experimentation to building production applications.

### Inference parameters

Inference parameters control how foundation models generate responses. These settings include temperature (controlling randomness), top-p (limiting token selection to higher probability options), and maximum token count (constraining response length).

Adjusting these parameters helps you balance creativity and determinism in model outputs. Lower temperature settings produce more predictable responses, and higher values increase variety and potentially creativity.

### RAG

Retrieval Augmented Generation (RAG) enhances foundation model outputs by incorporating information from external knowledge sources. This technique connects models to your data without requiring model retraining.

RAG implementations typically involve creating a knowledge base, retrieving relevant information based on user queries, and incorporating this information into the context provided to the foundation model. This approach improves accuracy for domain-specific applications.

### Model evaluation

Model evaluation involves systematically assessing foundation model performance across dimensions like accuracy, relevance, and safety. This process helps you select appropriate models and measure improvements from customization efforts.

Amazon Bedrock provides evaluation tools that help you compare models and track performance over time. Effective evaluation requires defining clear metrics aligned with your application requirements and business objectives.

### Flows

Flows in Amazon Bedrock are visual, no-code tools for orchestrating complex AI workflows. Users can design multi-step processes that combine different AI models, data sources, and logic operations. For example, a flow might extract information from a document, summarize it, and then generate a response based on that summary.

Bedrock Flows offer drag-and-drop functionality to connect various components, such as foundation models, knowledge bases, and custom functions. This approach streamlines the development of sophisticated AI applications, making AI accessible to users without extensive coding experience. Flows provide the flexibility to incorporate custom code when needed.

### Agents

Agents in Amazon Bedrock are AI-powered assistants that combine foundation models with custom actions and knowledge bases to perform specific tasks. These agents can interpret user requests, access designated data sources, run predefined functions, and maintain conversation context while adhering to set parameters and security protocols.

Consider a customer service agent built for an ecommerce platform: The agent accesses the product catalog, processes returns, tracks shipments, and answers policy questions. When a customer asks about returning a defective item, the agent checks the purchase history, explains the return policy, and initiates the return process through integrated backend systems.

### Security

Amazon Bedrock implements comprehensive security controls through AWS Identity and Access Management (IAM) policies, encryption at rest and in transit, and virtual private cloud (VPC) endpoints. The service integrates with AWS Key Management Service (AWS KMS) for key management and supports private network connectivity. And it maintains detailed API activity logs through AWS CloudTrail for auditing purposes.

For example, a healthcare organization uses Amazon Bedrock security features to process patient data securely. Their application runs in a private subnet, connects to Amazon Bedrock through VPC endpoints, and uses IAM roles to restrict model access. All data remains encrypted, and CloudTrail logs track every interaction for compliance requirements.

### Governance and guardrails

Governance in Amazon Bedrock provides organizations with control mechanisms to manage AI model usage, data handling, and compliance requirements. These controls include model access restrictions, prompt validation rules, and response filters. In addition, detailed usage monitoring through Amazon CloudWatch metrics and CloudTrail logs supports responsible AI deployment across the enterprise.

A financial services company implements guardrails for their customer service assistant. The guardrails prevent the model from discussing unauthorized financial products, filter out sensitive information in responses, and maintain audit logs of all interactions. Usage quotas limit API calls per department, and prompt templates standardize customer interactions.

## Amazon Bedrock key features and capabilities

---

Amazon Bedrock offers comprehensive features and capabilities designed to help organizations implement and scale generative AI solutions effectively.

Amazon Bedrock provides powerful features that enable organizations to use generative AI while maintaining security and control.

### Multi-model access

Amazon Bedrock provides access to a diverse portfolio of foundation models from leading AI providers through a single, unified API. This approach eliminates the need to manage separate relationships with multiple model providers or learn different interfaces for each model.

The service includes models optimized for different tasks and performance characteristics, such as Anthropic Claude models for conversational AI, Stability AI models for image generation, and Amazon Titan models. This variety lets you select the most appropriate model for each specific use case rather than forcing a one-size-fits-all approach.

### Model customization options

Amazon Bedrock offers multiple approaches to adapt foundation models to your specific requirements without deep machine learning expertise. The service supports fine-tuning, which adjusts model parameters using your own criteria to improve accuracy on domain-specific tasks.

For scenarios where you need models to access your proprietary information without retraining, Amazon Bedrock provides built-in support for RAG. This technique enhances model responses by retrieving relevant information from your data sources and incorporating it into the generation process to improve accuracy and relevance.

### Agents framework

Amazon Bedrock includes an agents framework that enables the creation of AI assistants capable of performing complex tasks through multi-step reasoning and tool use. These agents can maintain context across conversations and execute actions based on user requests.

The agents framework simplifies the development of applications that require orchestration between foundation models and external systems. You can define knowledge bases for agents to reference and configure API connections that allow agents to interact with your business systems, thus creating more capable and contextually aware AI applications.

Amazon Bedrock provides essential capabilities that enable organizations to maximize the value of generative AI.

### Enterprise security

Amazon Bedrock implements comprehensive security measures designed for enterprise requirements. The service processes your data within your AWS account boundaries and doesn't use your inputs or outputs to train the underlying models, which maintains data privacy. Additionally, Amazon Bedrock adheres to AWS robust compliance programs, which helps organizations meet various industry-specific and regional regulatory standards.

Amazon Bedrock integrates with AWS Identity and Access Management (IAM) for fine-grained access control and supports private endpoints through AWS PrivateLink for enhanced network security. These features, combined with AWS continuous compliance audits and certifications, help you meet stringent security and privacy compliance requirements while deploying generative AI applications at scale. The Amazon Bedrock compliance state is regularly updated and can be monitored through AWS Artifact, which ensures transparency and up-to-date compliance information.

### Serverless architecture

Amazon Bedrock operates on a fully managed, serverless architecture that eliminates infrastructure management concerns. The service automatically handles scaling to meet your application demands without requiring capacity planning or cluster management.

This serverless approach reduces operational overhead and helps you to focus on application development rather than infrastructure maintenance. The pay-as-you-go pricing model also aligns costs with actual usage, to improve cost efficiency compared to maintaining dedicated infrastructure.

### Responsible AI tools

Amazon Bedrock provides built-in tools for implementing responsible AI practices in your applications. The service includes content filtering capabilities that help prevent the generation of harmful or inappropriate content across text and image modalities. Additionally, customizable guardrails permit you to define and enforce boundaries on model behavior to ensure that outputs align with your organization's policies and ethical standards.

Model evaluation features help you assess model performance across dimensions like accuracy, relevance, and safety. These tools support systematic comparison between models and measurement of improvements from customization efforts, to help you make informed decisions about model selection and implementation. The combination of evaluation capabilities and configurable guardrails provides a comprehensive framework for responsible AI development and deployment.

## Amazon Bedrock practical business applications

---

Amazon Bedrock creates business value across industries. Organizations transform operations and gain competitive advantages without deep AI expertise or infrastructure investments.

### Content generation

Marketing teams use Amazon Bedrock to accelerate content creation workflows by generating drafts of blog posts, social media updates, and product descriptions. This capability helps maintain consistent messaging across channels while reducing the time required to produce new content.

The Amazon Bedrock image generation capabilities also support the creation of visual assets for marketing campaigns. The combination of text and image generation provides a comprehensive toolkit for content creators who want to increase productivity without sacrificing quality.

### Customer service

Amazon Bedrock powers intelligent customer service AI assistants that can understand complex queries and provide helpful, contextual responses. These solutions reduce wait times and improve customer satisfaction by handling routine inquiries automatically.

The foundation models in Amazon Bedrock can be customized with company-specific knowledge bases, to help AI assistants answer questions about products, policies, and procedures with accuracy. This application delivers significant cost savings while maintaining high-quality customer interactions.

### Data analysis and insights

Organizations implement Amazon Bedrock to extract insights from large document collections like contracts, research papers, or technical documentation. The service can summarize key points, identify patterns, and answer specific questions about document contents.

This application transforms unstructured information into actionable knowledge, to support better decision-making across departments. Legal teams particularly benefit from faster contract review processes, and research organizations gain efficiency in literature analysis.

### Product development assistance

Engineering and product teams use Amazon Bedrock to accelerate development processes through automated code generation, documentation creation, and problem-solving assistance. The service helps developers overcome technical challenges by suggesting solutions based on best practices.

Product managers use Amazon Bedrock to analyze customer feedback at scale and identify trends and opportunities for improvement. This application supports data-driven product decisions by processing and synthesizing information from diverse sources.

### Enterprise knowledge management systems

Organizations build internal knowledge management systems powered by Amazon Bedrock that make institutional knowledge accessible across the enterprise. These systems connect employees with information stored in various repositories through natural language interfaces.

The RAG capabilities in Amazon Bedrock assist these knowledge systems to provide accurate, up-to-date information from company databases and documents. This application improves operational efficiency by reducing time spent searching for information and providing consistent access to organizational knowledge.

## Check your knowledge

---

The following section will check your understanding of Amazon Bedrock.

### What is a core function of Amazon Bedrock?

- Amazon Bedrock provides access to foundation models from leading AI companies through a unified API.
- Amazon Bedrock creates custom machine learning models from scratch without requiring training data.
- Amazon Bedrock automatically generates documentation for all AWS services in your account.
- Amazon Bedrock translates legacy code into modern programming languages for application modernization.

SUBMIT

### What is a technical concept of Amazon Bedrock?

- Prompt engineering involves crafting effective instructions for foundation models to produce desired outputs.
- Network topology mapping is used to establish connection paths between foundation models.
- Quantum computing principles are applied when selecting appropriate foundation models.
- Binary translation is necessary to convert user inputs into a format foundation models can process.

SUBMIT

### What is a key feature of Amazon Bedrock?

- Amazon Bedrock provides physical robot control systems for automated warehouse operations.
- Amazon Bedrock has the ability to customize the models by incorporating updated or proprietary data.
- Amazon Bedrock creates custom hardware configurations for running AI models.
- Amazon Bedrock can generate real-time weather predictions using satellite data.

SUBMIT

### What is a practical business application of Amazon Bedrock?

- Organizations use Amazon Bedrock for content generation and technical documentation at scale.
- Organizations use Amazon Bedrock to manage physical inventory systems in warehouses.
- Organizations use Amazon Bedrock to control autonomous delivery drones in real time.
- Organizations use Amazon Bedrock to process financial transactions and banking operations.

SUBMIT

## Technical Overview for Amazon Bedrock

### Lesson objectives

By the end of this lesson, you will be able to do the following:

- Identify the elements of the Amazon Bedrock service architecture.
- Identify the key service integrations for Amazon Bedrock.

### Amazon Bedrock architecture

Amazon Bedrock runs as a fully managed, serverless framework that connects to foundation models through a unified interface. The framework includes foundation models, agents, knowledge bases, and evaluation tools.

#### Architecture diagram (Mermaid)

![Technical Overview for Amazon Bedrock architecture](./amazon_bedrock/bedrock-technical-overview.svg)

> If your viewer supports Mermaid, you can keep the Mermaid version as well. This SVG is added for universal Markdown image rendering.

To learn more, choose each of the numbered markers.

Architecture diagram showing an enterprise data flow with Amazon Bedrock, Amazon Lex, and external data.

1. **User query**  
Users or consumers query Amazon Lex through the UI, which is capable of understanding natural language.

2. **Compute and business logic**  
The query is processed and sent to the compute layer. AWS Lambda routes and orchestrates the request and response between services based on the business logic and user query.

3. **Relevant data**  
Enterprise data from various sources is stored in Amazon Simple Storage Service (Amazon S3) and synced to the Amazon Bedrock Knowledge Bases. This integration allows Bedrock to use RAG to enhance its responses with relevant organization-specific information, making the AI's outputs more accurate and contextually appropriate.

4. **Amazon Bedrock Knowledge Bases**  
Amazon Bedrock Knowledge Bases store and manage enterprise content that has been synced from Amazon S3. It processes and indexes this information to make it readily available for the foundation models to use in generating responses. This enables RAG by providing relevant context from enterprise data.

5. **Generative AI response**  
Amazon Bedrock uses FMs to get the query response. Then it routes that response back to Lambda for processing. An integrated development environment supports model discovery, testing, and application building with analysis tools.

6. **Response to user**  
The response is sent to the Amazon Lex user interface to provide a final natural language response to the users or consumers.

---

## Amazon Bedrock integrations

Amazon Bedrock works with your existing AWS infrastructure to help you build complete generative AI solutions that connect your data, compute resources, and application logic with strong security and scalability.

### Integration Overview

![Amazon Bedrock Integrations Ecosystem](./amazon_bedrock/bedrock-integrations.svg)

---

### Amazon SageMaker AI

SageMaker AI works alongside Amazon Bedrock to support the complete machine learning lifecycle. Although Amazon Bedrock provides foundation models through a simplified interface, SageMaker AI offers complementary capabilities for custom model development and deployment.

The integration creates workflows where data scientists use SageMaker AI for data preparation and feature engineering before using Amazon Bedrock for generative tasks. This combination provides flexibility for organizations that need both foundation models and custom machine learning models in their AI strategy.

### Amazon Kendra

Amazon Kendra enhances the Amazon Bedrock retrieval-augmented generation capabilities with enterprise search functionality. This integration connects foundation models to information stored across multiple repositories, including websites, file systems, and databases.

When combined with Amazon Bedrock, Amazon Kendra provides semantic search capabilities that understand the intent behind queries and retrieve relevant information. This powerful combination improves the accuracy and relevance of generative AI applications that need to incorporate enterprise knowledge.

### AWS Lambda

AWS Lambda runs code that orchestrates interactions between Amazon Bedrock and other services. This serverless compute service handles tasks like preprocessing inputs, formatting responses, and implementing business logic.

The integration with Amazon Bedrock provides event-driven architectures where Lambda functions call foundation models in response to triggers from other AWS services. This pattern supports complex workflows while maintaining a serverless operational model with automatic scaling.

### Amazon Simple Storage Service (Amazon S3)

Amazon S3 provides scalable object storage for data used with Amazon Bedrock. This integration supports multiple workflows, including storing documents for retrieval-augmented generation and managing datasets for fine-tuning.

Amazon Bedrock can directly access content stored in S3 buckets to streamline data workflows. This capability simplifies the process of connecting foundation models to your organization's information assets while using the durability and security features of Amazon S3.

### Amazon OpenSearch Service

OpenSearch Service works with Amazon Bedrock to implement efficient retrieval-augmented generation systems. This integration indexes documents and other content to enable semantic search capabilities that complement foundation models.

When a user query arrives, the system can search OpenSearch indices to find relevant information before passing it to Amazon Bedrock. This approach enhances model responses with specific, accurate information from your organization's data sources.

### AWS Identity and Access Management (IAM)

IAM controls access to Amazon Bedrock and related services. This integration implements fine-grained permissions that determine which users and applications can access specific foundation models and features.

IAM policies for Amazon Bedrock follow the principle of least privilege, ensuring that each entity has only the permissions required for its function. This security layer protects sensitive data and prevents unauthorized access to foundation models.

### Amazon CloudWatch

CloudWatch monitors the performance and health of Amazon Bedrock applications. This integration collects metrics, logs, and events that provide visibility into key performance indicators like response times, error rates, and usage patterns.

CloudWatch dashboards for Amazon Bedrock help identify issues and optimize performance. The service also supports alerts that notify you when metrics exceed thresholds, to enable proactive management of generative AI applications.

### Amazon EventBridge

EventBridge creates event-driven architectures that incorporate Amazon Bedrock capabilities. This integration enables systems where events from one service automatically trigger foundation model operations.

For example, a new document uploaded to Amazon S3 could trigger an EventBridge rule. That event invokes Amazon Bedrock APIs through a generative AI application to create a summary. This pattern supports automated workflows that process information as it enters your systems.

---

## Integration considerations

When integrating Amazon Bedrock with your existing systems, consider factors such as data security, model selection, and performance requirements to ensure optimal implementation.

### Security compliance

Your integrations should meet security requirements by implementing appropriate encryption, access controls, and compliance measures for data protection and governance.

**Next:** Review performance optimization best practices.

### Performance optimization

Balance model selection and configuration settings to achieve optimal performance while managing costs and meeting your application's specific needs.

**Next:** Consider scalability planning for your integration.

### Scalability planning

Design your integration to handle varying workloads efficiently, considering factors such as concurrent requests, response times, and resource utilization.

**Next:** You have reviewed all integration considerations.

---

## Amazon Bedrock Demonstrations

### Lesson objectives

By the end of this lesson, you will be able to use the AWS Management Console to complete the basic functions of Amazon Bedrock.

This lesson contains the following demos:

- Setting Up Amazon Bedrock Access
- Configuring Model Parameters in a Playground Session
- Creating Your First Amazon Bedrock Knowledge Bases
- Deleting Resources

> Performing the following demonstrations in an AWS account can have an associated cost. To avoid incurring fees, do not perform these demonstrations in your AWS environment. If you choose to perform the demonstrations in your environment, you must clean up any resources you create to avoid incurring additional unwanted fees.

### Numbered divider1 — Setting Up Amazon Bedrock Access

In this demo, you will learn how to set up access to models in Amazon Bedrock through the AWS Management Console.

This setup process empowers you to start experimenting with different models and their capabilities.

> Note: Amazon Bedrock and its models might not be available in all AWS Regions. This demo uses **US West (Oregon) `us-west-2`**. For a full list of supported Regions, see *Model support by AWS Region in Amazon Bedrock*.

#### Transcript: Setting Up Amazon Bedrock Access

Welcome to this demonstration on setting up access to models in Amazon Bedrock.

1. Enter **Bedrock** in the AWS Management Console search box, then choose **Amazon Bedrock**.
2. On the Amazon Bedrock Overview page, choose **View Model catalog**.
3. On the Model catalog page, review the full listing of models available in Amazon Bedrock.
4. Use the **Filters** panel to explore by provider, modality, and pricing model.
5. Note that many models (such as Amazon Nova Pro and Anthropic) are available as part of the standard set, while some are subscription/open-source-license based.

After exploring the catalog and narrowing your filters for your use case, this concludes the demonstration.

Thank you for your participation.

### Numbered divider2 — Configuring Model Parameters in a Playground Session

In this demo, you will learn how to configure and fine tune the parameters for your FMs.

Learn to configure model access and test basic prompts in the model playground. Compare outputs from different models to understand their varying capabilities.

> NOTE: The settings you adjust in this demonstration are specific to the playground environment and do not affect global model settings. In production applications, you would specify similar parameters per API call.

#### Story prompt example

Write a short story about a day in the life of an extraterrestrial visiting Earth for the first time.

#### Transcript: Configuring Model Parameters in a Playground Session

Welcome to this demonstration of configuring model parameters in a playground session.

1. In the AWS Management Console, search for **Bedrock** and choose **Amazon Bedrock**.
2. From the navigation panel, under **Test**, choose **Playground**.
3. In the chat playground, choose **Select model**.
4. In the dialog:
	- Choose a model provider (Categories)
	- Choose a model (Models)
	- Choose an inference profile
	- Choose **Apply**
5. In **Configurations**, go to **Randomness and diversity**.
6. Leave Temperature and Top P at default first (Top K is not the focus), then run this prompt:

	*Write a short story about a day in the life of an extraterrestrial visiting Earth for the first time.*

7. Review output and copy options:
	- Copy full conversation
	- Copy individual response
8. Keep **Temperature = 1**, set **Top P = 0.2**, run same prompt.
9. Set **Temperature = 0.2**, **Top P = 0.9**, run same prompt.
10. Keep **Temperature = 0.2**, set **Top P = 0.2**, run same prompt.

Compare the four outputs to understand how settings change creativity vs predictability.

Thank you for your participation.

#### Temperature and Top P reference image

![Temperature and Top P matrix](./amazon_bedrock/temperature-top-p-matrix.svg)

To download the four short stories generated in this demonstration:

- [short-story-variations.md](./amazon_bedrock/short-story-variations.md)

### Numbered divider3 — Creating Your First Amazon Bedrock Knowledge Base

In this demo, you will learn how to create an Amazon Bedrock Knowledge Base.

Create and manage knowledge bases to enhance model responses with your own information, while maintaining security and control over your data.

#### Example prompt

Describe the differences between few-shot and zero-shot prompting.

#### Transcript: Creating Your First Amazon Bedrock Knowledge Base

Welcome to this demonstration on creating your first Amazon Bedrock Knowledge Base.

1. In the AWS Management Console, search for **Bedrock** and choose **Amazon Bedrock**.
2. Choose **Knowledge Bases** from navigation.
3. Choose **Create** → **Knowledge Base with vector store**.
4. On **Provide Knowledge Base details**:
	- Enter a Knowledge Base name
	- In IAM permissions, choose **Create and use a new service role**
	- Verify Amazon S3 is selected as data source
	- Choose **Next**
5. On **Configure data source**:
	- Enter a data source name
	- Prepare and provide an S3 URI

##### Create S3 bucket for source docs

1. Open S3 console, go to **Buckets** → **General purpose buckets** → **Create bucket**.
2. Keep defaults for bucket type, ACLs disabled, and block public access on.
3. Enter unique bucket name and choose **Create bucket**.
4. Open the bucket and upload the course file **Amazon Bedrock Prompt Engineering PDF**.
5. Open object properties and copy the **S3 URI**.

##### Return to Knowledge Base setup

1. Paste the S3 URI in Bedrock data source configuration.
2. Leave chunking/parsing defaults and choose **Next**.
3. In Embeddings model section, choose **Select model** and apply model + inference.
4. In Vector store section:
	- Keep **Quick create a new vector store**
	- Choose **Amazon OpenSearch Serverless**
5. Review settings and choose **Create Knowledge Base**.

After creation:

1. Open data source and choose **Add documents**.
2. Browse S3 and select uploaded PDF.
3. Confirm S3 URI auto-populates and choose **Add**.
4. After ingestion completes, go back to Knowledge Bases and choose **Sync**.
5. When sync completes, choose **Test Knowledge Base**.
6. Select model in Retrieval and response generation.
7. Run prompt: *Describe the differences between few-shot and zero-shot prompting.*
8. Review response, then open **Details** to inspect retrieval/response generation behavior.

Thank you for your participation.

To download the file attachment used in this demo:

- [Amazon-Bedrock_Prompt-Engineering.pdf](./amazon_bedrock/Amazon-Bedrock_Prompt-Engineering.pdf)

### Deleting Resources

In this demo, you will learn how to remove the resources that you created during this lesson. You will use the AWS Management Console to delete your Knowledge Base and uploaded Amazon S3 documents to ensure cleanup and avoid additional cost.

#### Transcript: Deleting Resources

1. In AWS Console, search **Bedrock**, open **Amazon Bedrock**.
2. Choose **Knowledge Bases**.
3. Select your created Knowledge Base and choose **Delete**.
4. In confirmation dialog, enter `delete`, then choose **Delete**.
5. Wait for status to complete; KB should disappear from list.
6. Search **S3** in console and open bucket used for documents.
7. Select uploaded document(s), choose **Delete**.
8. Enter `permanently delete` and confirm **Delete objects**.
9. Select the bucket and choose **Delete**.
10. Enter bucket name in confirmation and choose **Delete bucket**.

A success banner should confirm object and bucket deletion.

Thank you for your participation.

---

## Implementation conversation log (provided context)

<details>
<summary>Click to expand implementation traceability notes</summary>

The following text captures the implementation context you asked to preserve in this document for traceability:

- Prompt window improvements were requested and implemented:
	- Add vertical scrollbar in textarea.
	- Press **Enter** to submit.
	- Press **Shift + Enter** for a new line.
- Conversation history behavior was requested and implemented:
	- Show prompt + timestamp + response entries.
	- Add scroll behavior for `.response-viewer` with max height.
	- Align user prompts to the right and responses to the left.
- Sample prompt UX was requested and implemented:
	- Add **Sample Prompts** button near **Generate**.
	- Open popup/modal with copyable sample prompts.
	- Keep button aligned to the left of controls.
- Documentation files were created and expanded:
	- `Introduction to AWS Elemental MediaConnect.md`
	- `Introduction to Amazon Bedrock.md`
- Visual references and diagrams were added for Bedrock and MediaConnect topics.
- Bedrock sections were expanded with:
	- Technical overview
	- Integrations
	- Demonstrations
	- Resource cleanup steps
- Diagram rendering issue was resolved by using image-based SVG references.

</details>

---

## amazon_bedrock reference files

Use the following files in `amazon_bedrock` for quick access:

- [Amazon-Bedrock_Prompt-Engineering.pdf](./amazon_bedrock/Amazon-Bedrock_Prompt-Engineering.pdf)
- [short-story-variations.md](./amazon_bedrock/short-story-variations.md)
- [bedrock-technical-overview.svg](./amazon_bedrock/bedrock-technical-overview.svg)
- [bedrock-integrations.svg](./amazon_bedrock/bedrock-integrations.svg)
- [temperature-top-p-matrix.svg](./amazon_bedrock/temperature-top-p-matrix.svg)

### Quick visual references

![Technical Overview diagram](./amazon_bedrock/bedrock-technical-overview.svg)

![Bedrock integrations diagram](./amazon_bedrock/bedrock-integrations.svg)

![Temperature vs Top P matrix](./amazon_bedrock/temperature-top-p-matrix.svg)

---

## Amazon Bedrock user guides

To learn more information about Amazon Bedrock, review the following:

- **Amazon Bedrock Official Guide**  
	[USER GUIDE](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html)

- **Amazon Bedrock Code Examples**  
	[CODE EXAMPLES](https://docs.aws.amazon.com/bedrock/latest/userguide/service_code_examples.html)

- **Amazon Bedrock API Reference**  
	[API REFERENCE](https://docs.aws.amazon.com/bedrock/latest/APIReference/welcome.html)

## Use cases and best practices for Amazon Bedrock

To learn more about use cases and implementation best practices, review the following:

- **Amazon Bedrock Blogs**  
	[AWS BLOGS](https://aws.amazon.com/blogs/machine-learning/category/artificial-intelligence/amazon-machine-learning/amazon-bedrock/)

- **Ask the Amazon Bedrock Team**  
	[RE:POST](https://repost.aws/tags/TAQeKlaPaNRQ2tWB6P7KrMag/amazon-bedrock)

- **AWS Well-Architected Framework**  
	[FRAMEWORK](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)

## Amazon Bedrock pricing

To learn more about pricing for Amazon Bedrock, review the following:

- **Amazon Bedrock Pricing**  
	[PRICING](https://aws.amazon.com/bedrock/pricing/)

- **AWS Pricing Calculator**  
	[PRICING CALCULATOR](https://calculator.aws/)
