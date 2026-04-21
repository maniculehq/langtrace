# Langtrace — Scraped Documentation

**Source:** https://langtrace.ai
**Pages scraped:** 15
**Total characters:** 51453

---

## 

**URL:** https://docs.langtrace.ai/concepts.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Concepts
Exploring some of the key concepts to understand when using Langtrace for your traces.
### [Span](https://opentelemetry.io/docs/concepts/signals/traces/#spans)
A [span](https://opentelemetry.io/docs/concepts/signals/traces/#spans) represents a unit of work or operation. Spans are the building blocks of Traces. In OpenTelemetry, they include the following information:
* Name
* Parent span ID (empty for root spans)
* Start and End Timestamps
* Span Context
* Attributes
* Span Events
* Span Status
### [Trace](https://opentelemetry.io/docs/concepts/signals/traces/)
A [Trace](https://opentelemetry.io/docs/concepts/signals/traces/) represents the entire journey of a request through the LLM system, composed of multiple spans. It provides a complete picture of all operations involved in processing the request, aiding in system performance evaluation and issue identification.
### Metric
A Metric is a quantifiable measure used to evaluate the performance and effectiveness of an LLM. Common metrics include token usage, cost, latency and accuracy. Metrics provide objective criteria for assessing the application's accuracy, usage and performance over time.
### Project
A Project in monitoring terms is a logical grouping of traces that correspond to a specific application or service. It acts as a container, organizing traces to simplify management and analysis. Within a single project, you can monitor various aspects of the application's performance and behavior through its traces. Having multiple projects allows for clear separation and focused monitoring of different applications or services within an organization.
### Dataset
A Dataset refers to a structured collection of data used to train, test, or validate a Large Language Model (LLM). Datasets are crucial for developing and refining LLMs, as they provide the raw material on which these models learn and improve. Langtrace will automatically surface the request and responses captured by the traces under the evaluation tab. You can choose to create a dataset and add specific request response pairs to it.
### Evaluation
Evaluation in LLM monitoring is the process of assessing the model's performance and effectiveness. Evaluation helps in understanding how well the model meets the desired outcomes and in identifying areas for improvement.
In Langtrace, you can evaluate the accuracy of the responses in a couple of ways:
* If you application collects feedback from users, you can pass the feedback score down to the traces using the Langtrace SDK.
* You can manually evaluate the responses and provide a score from the evaluation tab.
Langtrace also lets you create tests and evaluate the captured input-output pairs against the expected output. You can create tests and evaluate the responses against the expected output.

---

## 

**URL:** https://docs.langtrace.ai/hosting/overview.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Overview
> You can self-host Langtrace to monitor your applications. This guide will help you set up Langtrace on your own infrastructure.
## Self-hosting Langtrace
To run Langtrace locally, you have to run three services:
* Next.js app
* Postgres database
* Clickhouse database
### Configure Langtrace SDK
To configure the Langtrace SDK for self-hosted setups, checkout the guide [here](/hosting/using_local_setup).
### Authentication Setup
Langtrace supports multiple authentication methods, including Admin Password, Google OAuth, and Azure AD OAuth. For detailed instructions on configuring authentication for your self-hosted setup, refer to our [Authentication](/hosting/auth) guide.
### Setup Guides
> Video Guide Playlist for Langtrace Setups [here](https://www.youtube.com/playlist?list=PL1oUBNzZiq8cfdHvJJ5YN5qO4P_6uA6CP).
Run standalone instance of Langtrace docker container
Run Langtrace with all required databases using docker-compose
Run Langtrace on Kubernetes using Helm Chart
Run Langtrace on Azure AppService
Run Langtrace on Railway with a single click!

---

## 

**URL:** https://docs.langtrace.ai/introduction.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Introduction
> Welcome to the Langtrace AI documentation
[Langtrace](https://langtrace.ai/) is an open-source observability tool that collects and analyze traces in order to help you improve your LLM apps. Langtrace has two components:
* **SDK**: The SDK is a lightweight library that can be installed and imported into your project in order to collect traces. The [traces](https://opentelemetry.io/docs/concepts/signals/traces/) are [open telemetry](https://opentelemetry.io/) based and can be exported to Langtrace or any other observability stack (Grafana, Datadog, Honeycomb etc) without having to use a Langtrace API key.
**GitHub**: [`Python SDK`](https://github.com/Scale3-Labs/langtrace-python-sdk)
[`Typescript SDK`](https://github.com/Scale3-Labs/langtrace-typescript-sdk) [`trace-attributes`](https://github.com/Scale3-Labs/langtrace-trace-attributes)
* **Langtrace Dashboard**: The dashboard is a web-based interface where you can view and analyze your traces.
**GitHub**: [`Langtrace`](https://github.com/Scale3-Labs/langtrace)
**[OpenTelemetry](https://opentelemetry.io/)**: The traces generated by
Langtrace are based on the OpenTelemetry standard. This means that you can use
Langtrace with your existing observability stack (No Langtrace API key
required.), or export the traces to Langtrace.
Langtrace optimizes for the following 3 pillars of observability for your LLM apps:
* Usage - Tokens and Cost
* Accuracy
* Performance - Latency and Success Rate
Need help with the SDK? [Contact us](https://calendar.app.google/Go5gXNPcqZjAY4i47)
## Setting up
The first step to using Langtrace is to import into your Typescript or Python project.
#### Step 1: Signup to Langtrace and generate an API key from the Langtrace dashboard.
* Signup to Langtrace [here](https://app.langtrace.ai/signup)
* Go to the [Langtrace dashboard](https://app.langtrace.ai/projects)
* Create a new project, be sure to provide a name and description
* Click on the Project name
* Click on the `Generate API Key` button
* Copy the generated API key. You will need this key to initialize the SDK in your project.
#### Step 2: Install the SDK on your project:
* **Python**: Install the Langtrace SDK using pip
```python theme={null}
pip install langtrace-python-sdk
```
* **Typescript**: Install the Langtrace SDK using npm
```typescript theme={null}
npm i @langtrase/typescript-sdk
```
#### Step 3: Initialize the SDK in your project:
```typescript Typescript theme={null}
// Must precede any llm module imports
import * as Langtrace from "@langtrase/typescript-sdk";
Langtrace.init({ api_key: "
" });
```
```python Python theme={null}
from langtrace_python_sdk import langtrace
langtrace.init(api_key = '
')
```
#### Step 3: Run your application to view your traces on the Langtrace dashboard.
You can now view your traces on the [Langtrace dashboard](https://app.langtrace.ai/projects).
## Start using Langtrace
Dive into the SDK features. Here are the supported languages
Integrate with your Python project
Integrate with your Typescript project
We are working hard to add support for more languages.
## Pricing
Langtrace offers flexible pricing options to suit various needs and usage levels. Here's an overview of our pricing structure:
## Starter
Ideal for individuals or hackers just beginning their LLM observability journey.
* Free forever
* 1 user/month
* Includes up to 10K spans/month, prompt management, and evaluations
## Growth
Designed for growing teams and projects with increasing observability needs.
* \$39/user/month
* Usage based pricing: \$0.005 / additional span ingested / month (above 50K spans)
* Includes everything in Free Forever
* Evaluations in the cloud
* Team collaboration features
* Security guardrails
## Scale - Enterprises
Tailored solutions for large-scale enterprises with complex requirements.
* Custom pricing
* Custom retention policy
* Custom SLAs
* Security guardrails
* Team collaboration features
* SOC 2 Type II Compliance
## Self-Hosted
Perfect for developers who prioritize data control and customization.
* Free to get started
* Includes tracing, prompt management, and evaluations that can be accessed by hosting locally
## Pricing FAQs
### What is a span?
A span represents a single unit of work or operation in your application. For LLM apps, this typically corresponds to an API call or a specific step in your language model pipeline.
### How do I know which plan is right for me?
If you're just getting started or want to self-host, our Self-Hosted option is perfect. For small teams or projects using our managed service, the Starter plan is ideal. As your usage grows, the Growth plan offers more flexibility and features. Large enterprises with specific needs should consider our Scale plan.
### Can I upgrade or downgrade my plan?
Yes, you can change your plan at any time to match your current needs.
### What happens if I exceed my plan's limits?
For the Growth plan, you'll be charged for additional spans above the 50K limit. For other plans, please contact our sales team [sales@langtrace.ai](mailto:sales@langtrace.ai) to discuss options.
### Do you offer a free trial of paid features?
Please contact our sales team to discuss trial options for our paid features.
To discuss specific requirements or to learn more about our Enterprise offerings, please contact us at [sales@langtrace.ai](mailto:sales@langtrace.ai).
## FAQs
* **What is Langtrace?**
Langtrace is an open-source observability tool that helps you collect and analyze traces to improve your LLM apps.
* **How do I get started with Langtrace?**
To get started with Langtrace, you need to signup and generate an API key. Then, install and import the SDK into your project to start shipping traces to Langtrace.
* **What are the benefits of using Langtrace?**
Langtrace helps you with the following:
* Monitor your LLM usage - token and costs, latency and success rate.
* Evaluate the responses of the LLM to measure the accuracy of your LLM apps.
* Create and manage datasets and prompt sets for your LLM apps.
* **What languages does Langtrace support?**
Langtrace currently supports Python and Typescript. We are adding support for more languages.

---

## 

**URL:** https://docs.langtrace.ai/quickstart.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Quickstart
> Start shipping traces to Langtrace Cloud or your preferred OpenTelemetry-compatible backend in under 5 minutes!
### Introduction
Langtrace offers flexible options for trace collection and analysis:
1. **[Langtrace Cloud](#langtrace-cloud) ☁️**: Our managed SaaS solution for easy setup and immediate insights.
2. **[Self-hosted Langtrace](#langtrace-self-hosted) 🏠**: For organizations that prefer to host Langtrace on their own infrastructure.
3. **[OpenTelemetry Integration](#opentelemetry-integration) 🔗**: Langtrace SDK supports sending traces to any OpenTelemetry-compatible backend (Datadog, New Relic, Grafana, etc), allowing you to use your existing observability stack.
Important: When using Langtrace with third-party OpenTelemetry-compatible
vendors, you don't need to generate a Langtrace API key. The SDK can be
configured to send traces directly to your preferred backend.
Choose the option that best fits your needs and follow the corresponding setup instructions below.
#### Langtrace Cloud ☁️
To use the managed SaaS version of Langtrace, follow these steps:
1. Sign up by going to [this link](https://app.langtrace.ai/signup).
2. Create a new Project after signing up. Projects are containers for storing traces and metrics generated by your application. If you have only one application, creating 1 project will do.
3. Generate an API key. This key will be used to authenticate your application with Langtrace Cloud.
You may also create new projects and generate API keys for each of them
later.
4. In your application, install the Langtrace SDK. The code for installing the SDK is shown below:
```typescript Typescript theme={null}
// Install the SDK
npm i @langtrase/typescript-sdk
```
```python Python theme={null}
# Install the SDK
pip install langtrace-python-sdk
```
5. Initialize the Langtrace SDK with the API key you generated in the step 3. The code for setting up the SDK is shown below:
```typescript Typescript theme={null}
// Import it into your project. Must precede any llm module imports
import \* as Langtrace from '@langtrase/typescript-sdk'
Langtrace.init({ api_key: '
'})
```
```python Python theme={null}
# Import it into your project
from langtrace_python_sdk import langtrace # Must precede any llm module imports
langtrace.init(api_key = '
')
```
6. You can now use Langtrace in your code. Here's a simple example:
```python Python theme={null}
from openai import OpenAI
client = OpenAI()
response = client.chat.completions.create(
model="gpt-3.5-turbo",
messages=[
{"role": "system", "content": "You are a helpful assistant."},
{"role": "user", "content": "Hello!"}
]
)
print(response.choices[0].message)
```
```typescript Typescript theme={null}
import OpenAI from 'openai';
const openai = new OpenAI();
async function main() {
const completion = await openai.chat.completions.create({
messages: [
{ role: 'system', content: 'You are a helpful assistant.' },
{ role: 'user', content: 'Hello!' }
],
model: 'gpt-3.5-turbo',
});
console.log(completion.choices[0].message.content);
}
main();
```
Congrats! You can now view your traces on Langtrace Cloud. 🚀
#### OpenTelemetry Integration 🔗
If you prefer to use Langtrace with your existing OpenTelemetry-compatible backend:
1. Install the Langtrace SDK as described in the Langtrace Cloud section.
2. Instead of initializing with a Langtrace API key, configure the SDK to use your OpenTelemetry exporter. Refer to our [documentation](supported-integrations/overview#observabililty-tools) for OpenTelemetry tools. Or consult your platform of choice.
**Note:** When shipping traces directly to other observability tools (e.g.,
Datadog, Instana, New Relic), you **do not** need a Langtrace API key. Only the API key
for your chosen observability tool is required.
#### Langtrace Self-hosted 🏠
For users/organizations that want to host Langtrace on their own infrastructure, follow [these steps](hosting/overview) to get started.
### Configure Langtrace SDK
For more details on configuring the Langtrace SDK, refer to the page [Langtrace SDK Features](./sdk/sdk_features)
| Parameter                  | Type                                        | Default Value                        | Description                                                                                                                                        |
| -------------------------- | ------------------------------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| `batch`                    | `bool`                                      | `True`                               | Whether to batch spans before sending them.                                                                                                        |
| `api_key`                  | `str`                                       | `LANGTRACE_API_KEY`
or `None` | The API key for authentication.                                                                                                                    |
| `write_spans_to_console`   | `bool`                                      | `False`                              | Whether to write spans to the console.                                                                                                             |
| `custom_remote_exporter`   | `Optional[Exporter]`                        | `None`                               | Custom remote exporter.
If `None`, a default `LangTraceExporter` will be used.                                                              |
| `api_host`                 | `Optional[str]`                             | `https://langtrace.ai/`              | The API host for the remote exporter.                                                                                                              |
| `service_name`             | `Optional[str]`                             | `None`                               | The Service name for initializing langtrace                                                                                                        |
| `disable_instrumentations` | `Optional`
`[DisableInstrumentations]` | `None`                               | You can pass an object to disable instrumentation for specific vendors,
e.g., `{'only': ['openai']}`
or `{'all_except': ['openai']}`. |
| Parameter                      | Type                                                                 | Default Value                 | Description                                                                                                                                                                                          |
| ------------------------------ | -------------------------------------------------------------------- | ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `api_key`                      | `string`                                                             | `LANGTRACE_API_KEY` or `None` | The API key for authentication.                                                                                                                                                                      |
| `batch`                        | `boolean`                                                            | `false`                       | Whether to batch spans before sending them.                                                                                                                                                          |
| `write_spans_to_console`       | `boolean`                                                            | `false`                       | Whether to write spans to the console.                                                                                                                                                               |
| `custom_remote_exporter`       | `SpanExporter`                                                       | `undefined`                   | Custom remote exporter. If `undefined`, a default `LangTraceExporter` will be used.                                                                                                                  |
| `api_host`                     | `string`                                                             | `https://langtrace.ai/`       | The API host for the remote exporter. For self hosted setups the url needs to be appended with `/api/trace`.                                                                                         |
| `instrumentations`             | `{ [key in InstrumentationType]?: any }`                             | `undefined`                   | This is a required option for next.js applications. It is used to enable or disable instrumentations. ex `instrumentations: {openai: openai}` where the value is `import * as openai from 'openai'`. |
| `service_name`                 | `Optional[str]`                                                      | `undefined`                   | The Service name for initializing langtrace. Can also be set via `OTEL_SERVICE_NAME` environment variable                                                                                            |
| `disable_instrumentations`     | `{all_except?: InstrumentationType[], only?: InstrumentationType[]}` | `{}`                          | You can pass an object to disable instrumentation for specific vendors, e.g., `{'only': ['openai']}` or `{'all_except': ['openai']}`.                                                                |
| `disable_tracing_for_methods`  | `Partial
`                                             | `undefined`                   | You can pass an object to disable tracing for specific methods. ex `disable_tracing_for_methods: { openai: ['openai.chat.completion'] }`. Full list of methods can be found [here]()                 |
| `disable_latest_version_check` | `boolean`                                                            | `false`                       | Disable the latest version check. This disables the warning when the sdk version is outdated                                                                                                         |

---

## 

**URL:** https://docs.langtrace.ai/supported-integrations/overview.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Overview
> Langtrace supports a variety of LLMs, Frameworks and Vector databases.
Langtrace automatically captures traces from the following vendors:
| Vendor                                                              | Type            | Typescript SDK | Python SDK |                                                          Cookbook                                                         |
| ------------------------------------------------------------------- | :-------------- | :------------: | :--------: | :-----------------------------------------------------------------------------------------------------------------------: |
| [OpenAI](/supported-integrations/llm-tools/openai)                  | LLM             |        ✔       |      ✔     |    [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/language-model/openai/starter.ipynb)    |
| [Anthropic](/supported-integrations/llm-tools/anthropic)            | LLM             |        ✔       |      ✔     |   [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/language-model/anthropic/starter.ipynb)  |
| [Azure OpenAI](/supported-integrations/llm-tools/azure-openai)      | LLM             |        ✔       |      ✔     | [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/language-model/azure-openai/starter.ipynb) |
| [Cohere](/supported-integrations/llm-tools/cohere)                  | LLM             |        ✘       |      ✔     |    [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/language-model/cohere/starter.ipynb)    |
| [Groq](/supported-integrations/llm-tools/groq)                      | LLM             |        ✘       |      ✔     |                                                             -                                                             |
| [Groq](/supported-integrations/llm-tools/gemini)                    | LLM             |        ✘       |      ✔     |                                                             -                                                             |
| [Perplexity](/supported-integrations/llm-tools/perplexity)          | LLM             |        ✔       |      ✔     |       [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/tools/perplexity/starter.ipynb)      |
| [Mistral AI](/supported-integrations/llm-tools/mistral-ai)          | LLM             |        ✔       |      ✔     |                                                                                                                           |
| [KubeAI](/supported-integrations/llm-tools/kubeai)                  | LLM             |        ✔       |      ✔     |                                                             -                                                             |
| [Vercel AI SDK](/supported-integrations/llm-frameworks/vercelaisdk) | Framework       |        ✔       |      ✘     |                                                             -                                                             |
| [Langchain](/supported-integrations/llm-frameworks/langchain)       | Framework       |        ✘       |      ✔     |   [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/llm-framework/langchain/starter.ipynb)   |
| [LlamaIndex](/supported-integrations/llm-frameworks/llamaindex)     | Framework       |        ✔       |      ✔     |   [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/llm-framework/llamaindex/starter.ipynb)  |
| [Langgraph](/supported-integrations/llm-frameworks/langchain)       | Framework       |        ✘       |      ✔     |   [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/llm-framework/langchain/starter.ipynb)   |
| [DSPy](/supported-integrations/llm-frameworks/dspy)                 | Framework       |        ✘       |      ✔     |                                                             -                                                             |
| [CrewAI](/supported-integrations/llm-frameworks/crewai)             | Framework       |        ✘       |      ✔     |     [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/llm-framework/crewai/starter.ipynb)    |
| [Ollama](/supported-integrations/llm-tools/ollama)                  | Framework       |        ✘       |      ✔     |   [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/tools/ollama/ollama-fashionista.ipynb)   |
| [Mem0](/supported-integrations/llm-frameworks/mem0)                 | Framework       |        ✘       |      ✔     |      [Link](https://github.com/Scale3-Labs/langtrace-python-sdk/blob/main/src/examples/embedchain_example/simple.py)      |
| [Pinecone](/supported-integrations/vector-stores/pinecone)          | Vector Database |        ✔       |      ✔     |      [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/vector-db/pinecone/starter.ipynb)     |
| [ChromaDB](/supported-integrations/vector-stores/chromadb)          | Vector Database |        ✔       |      ✔     |     [Link ](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/vector-db/chromadb/starter.ipynb)     |
| [Qdrant](/supported-integrations/vector-stores/qdrant)              | Vector Database |        ✔       |      ✔     |       [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/vector-db/qdrant/starter.ipynb)      |
| [Weaviate](/supported-integrations/vector-stores/weaviate)          | Vector Database |        ✔       |      ✔     |      [Link](https://github.com/Scale3-Labs/langtrace-recipes/blob/main/integrations/vector-db/weaviate/starter.ipynb)     |
| [PGVector](https://github.com/pgvector/pgvector/)                   | Vector Database |        ✔       |      ✔     |                                                             -                                                             |
If you would like to see support for a specific vendor, please [contact us](https://calendar.app.google/Go5gXNPcqZjAY4i47) and let us know!
## Observabililty Tools
Langtrace traces are OpenTelemetry compatible so you can export traces to your preferred choice of observability tool such as Datadog, Grafana, New Relic, etc. Use the guides below to set up traces for your chosen platform. Refer to the guide for your specific tool for additional information.
**Note:** When shipping traces directly to other observability tools (e.g.,
Datadog, Instana, New Relic), you **do not** need a Langtrace API key. Only the API key
for your chosen observability tool is required.
* [Dash0](supported-integrations/observability-tools/dash0.mdx)
* [Elastic](supported-integrations/observability-tools/elastic.mdx)
* [Grafana](supported-integrations/observability-tools/grafana.mdx)
* [Honeycomb](supported-integrations/observability-tools/honeycomb.mdx)
* [Signoz](supported-integrations/observability-tools/signoz.mdx)

---

## 

**URL:** https://docs.langtrace.ai/tracing/overview.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Tracing Overview
Tracing is a fundamental feature of Langtrace that enables the collection and analysis of data from your LLM applications. This overview introduces key concepts and components of the tracing system.
## What is Tracing?
In the context of Langtrace, tracing refers to the process of capturing detailed information about the execution of your LLM apps. This includes data such as:
* Input and output tokens
* Response times
* Model parameters
* User feedback
* Custom attributes
## Core Components
### SDK
The Langtrace SDK is the primary tool for implementing tracing in your application. It:
* Integrates easily with your existing codebase
* Collects traces automatically
* Allows for custom attribute tracking
### Dashboard
The Langtrace Dashboard provides a web interface for:
* Visualizing collected traces
* Analyzing performance metrics
* Identifying trends and anomalies
## Next Steps
The following sections will dive deeper into specific tracing features and provide implementation guides for various use cases.

---

## 

**URL:** https://docs.langtrace.ai/contact/contact-us.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Contact Us
Need help or discuss your requirements?
We are here to help you with any questions you may have.
You can reach out to us through the following channels:
Join our channel to get help from the community.
Email us if you need any help or have any questions.
Create Issues on for any bugs or feature requests.
Book a meeting with us to discuss your requirements.

---

## 

**URL:** https://docs.langtrace.ai/faqs.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# FAQs
> Welcome to the Langtrace AI FAQs page. Here you will find answers to the most frequently asked questions about Langtrace.
## FAQs
* **What is Langtrace?**
Langtrace is an open-source observability tool that helps you collect and analyze traces to improve your LLM apps.
* **How do I get started with Langtrace?**
To get started with Langtrace, you need to signup and generate an API key. Then, install and import the SDK into your project to start shipping traces to Langtrace.
* **What are the benefits of using Langtrace?**
Langtrace helps you with the following:
* Monitor your LLM usage - token and costs, latency and success rate.
* Evaluate the responses of the LLM to measure the accuracy of your LLM apps.
* Create and manage datasets and prompt sets for your LLM apps.
* **What languages does Langtrace support?**
Langtrace currently supports Python and Typescript. We are adding support for more languages.
* **Pricing**
Langtrace is completely Free to use at the moment. We are mainly looking for feedback. However, please note that this is subject to change in the future.

---

## 

**URL:** https://docs.langtrace.ai/features/annotations.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Annotations
> Langtrace allows you to create tests and manually annotate your traces to evaluate the performance and create datasets for running evaluations.
## How to create tests
To create a tests, create a project and go to the Annotations tab. Click on the `Create Test` button and provide the following details:
* **Name**: A unique name for the test.
* **Description**: A brief description of the test.
* **Pick a Scale**: Choose the scale on which you want to evaluate the test. You can choose among the following options:
* **Binary**: Choose this option if you want to evaluate the test on a binary scale.
* **Rating**: Choose this option if you want to evaluate the test on a rating scale.
## Start Annotating
Once you have created a test and captured traces to it, you can start annotating the captured traces. Go to the Annotations tab and use the scale you picked while creating the test to annotate the test. The chart at the top will show you how the scores are trending over time.
## Add to Dataset
Once annotated or while annotating, you can add the traces to a dataset. This will allow you to run evaluations on the dataset and get insights into the performance of your application. To add traces to a dataset, click on the checkbox button on the first column of each row and click on the `Add to Dataset` button.

---

## 

**URL:** https://docs.langtrace.ai/features/compare-evaluations.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Compare Evaluations
> Langtrace allows you compare evaluations run on different models to understand the performance of your application across different models.
## How to compare evaluations
Go to the Evaluations tab in the Langtrace dashboard and select the evaluations you want to compare by clicking on the checkbox button on the first column of each row. Then, click on the 'Compare' button to compare the evaluations.

---

## 

**URL:** https://docs.langtrace.ai/features/evaluations.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Evaluations
> Langtrace allows you run evaluations on annotated datasets and get insights on the performance of your application.
## What are evaluations?
If you are using LLMs to build applications, it is important to evaluate the performance of your models. Evaluations help you understand how well your models are performing and identify areas for improvement. For example: If you are using GPT-3.5-Turbo to build a chatbot, and you want to switch to a different model, you can run evaluations to compare the performance of the two models and choose the one that works best for your application.
## How to run evaluations
Langtrace relies on [Inspect AI](https://ukgovernmentbeis.github.io/inspect_ai/), an Open Source framework for large language model evaluations created by the [UK AI Safety Institute](https://www.gov.uk/government/news/ai-safety-institute-releases-new-ai-safety-evaluations-platform). You can run evaluations on annotated datasets as well as your own datasets.
Inspect provides many built-in components, including facilities for prompt engineering, tool usage, multi-turn dialog, and model graded evaluations. Extensions to Inspect (e.g. to support new elicitation and scoring techniques) can be provided by other Python packages.
In order to run evaluations, you need to have a dataset that has been annotated or curated with Langtrace. To annotate a dataset, you can follow the steps in the [Annotate & Measure](/features/annotations) guide. Once you have an annotated dataset, follow the steps below to run evaluations.
1. Setup a project on Langtrace, trace a bunch of LLM completions and create a dataset out of the traced completions.
2. Create an independent python project and install Inspect AI
```
pip install inspect-ai
```
3. Add the LANGTRACE\_API\_KEY to your environment variables as shown below. **Note**: If you don't have an API key, you can generate one by following the steps in the [Generate API Key](/quickstart) guide.
```bash theme={null}
export LANGTRACE_API_KEY=
```
If you are self-hosting, set the LANGTRACE\_API\_HOST environment variable to the URL of your Langtrace instance.
```bash theme={null}
export LANGTRACE_API_HOST=
```
4. Copy the dataset ID from Langtrace and replace `
` in the script below
5. Write a simple evaluation script and save it in a file called `example_eval.py`
In the following example, we are going to run the dataset we created against different models and evaluate the performance of the models using Inspect AI & Langtrace.
The script below has a `plan` which includes a `generate()` step which will run each sample in the dataset against the specified model and a `self_critique()` step which will evaluate the performance of the model using the `model_graded_fact()` scorer.
The `self_critique()` step will compare the model's output with the ground truth and assign a score to the model based on how well it performed and it uses gpt-4o as the model to judge the performance of the model.
```python theme={null}
from inspect_ai import Task, task
from inspect_ai.dataset import csv_dataset
from inspect_ai.scorer import model_graded_fact
from inspect_ai.solver import self_critique, generate
@task
def example_eval():
return Task(
dataset=csv_dataset("langtracefs://
"),
plan=[
generate(),
self_critique(model="openai/gpt-4o")
],
scorer=model_graded_fact()
)
```
6. Run the evaluation script
Let's run this against a few different models using the command below
```bash theme={null}
inspect eval example_eval.py --model openai/gpt-3.5-turbo --log-dir langtracefs://
inspect eval example_eval.py --model openai/gpt-4o-mini --log-dir langtracefs://
inspect eval example_eval.py --model anthropic/claude-3-5-sonnet-20240620 --log-dir langtracefs://
inspect eval example_eval.py --model ollama/llama3.1 --log-dir langtracefs://
```
**Note**: In order to run the command above you will need to add your API keys for the models you are running the generations against. Additionally, set the `INSPECT_LOG_FORMAT=json` environment variable before running the inspect command to ensure outputs are generated in JSON format and properly uploaded to Langtrace for reporting.
7. Once the evaluations are complete, you can view the results in the Langtrace dashboard by going to the evaluations page inside the dataset you ran the evaluations on.
As you can see from the radar graph, you can compare the performance of the different models and see which one performed the best.
8. Additionally, you can also configure the `--log-dir` as an environment variable as shown below:
```bash theme={null}
export INSPECT_LOG_DIR=langtracefs://
```
Additional options for configuring your environment can be found in the [Inspect AI documentation](https://ukgovernmentbeis.github.io/inspect_ai/workflow.html#sec-workflow-configuration).
You can read more about Inspect AI and its capabilities in the [Inspect AI
documentation](https://ukgovernmentbeis.github.io/inspect_ai/).

---

## 

**URL:** https://docs.langtrace.ai/features/manage_prompts.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Manage Prompts
> Langtrace lets you store and version prompts, making it easy to manage and reuse them across your applications.
## How to create and version prompts
Step 1: Create a new project in Langtrace and go to the Prompts tab. Click on the "Create Prompt" button to create a new prompt.
You can define variables like `${name}` and `${version}` in your prompt. These variables can be dynamically filled in when you use the prompt in your application using the SDK.
Step 2: Once you have created a prompt, you can make it available by clicking the "Go Live" button. This will make the prompt available for use in your applications by default when you fetch it using the SDK. You can also create a new version of the prompt by clicking the "Update Prompt" button.
Step 3: Use the prompt in your application by fetching it using the SDK. You can pass variables to the prompt to fill in the placeholders.
```python Python theme={null}
// Must precede any llm module imports
import json
from langtrace_python_sdk import get_prompt_from_registry
response = get_prompt_from_registry(
, options={"prompt_version": 1, "variables": {"topic": "Healthcare", "rule1": "Be polite", "rule2": "If you do not know the answer, say I do not know. Do NOT make up stuff" } })
prompt = response['value']
# for json prompts (ex: tool calling)
# prompt = json.loads(prompt)
print(prompt)
```
```typescript Typescript theme={null}
# Must precede any llm module imports
import { getPromptFromRegistry } from '@langtrase/typescript-sdk'
const response = await getPromptFromRegistry(
, options={"prompt_version": 1, "variables": {"topic": "Healthcare", "rule1": "Be polite", "rule2": "If you do not know the answer, say I do not know. Do NOT make up stuff" } })
prompt = response['value']
# for json prompts (ex: tool calling)
# prompt = json.loads(prompt)
print(prompt)
```
Step 4: You can also fetch a specific version of the prompt by passing the version number in the options. And you can get the "Prompt Registry ID" from the Langtrace UI.
That's it! You have successfully created and versioned a prompt in Langtrace. You can now use this prompt in your applications and easily manage and reuse it across your projects.

---

## 

**URL:** https://docs.langtrace.ai/features/manage_zod_schema.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Manage Zod Schema for Tool Calling
> Langtrace lets you store and version Zod schemas for tool calling, making it easy to manage and reuse them across your applications.
## How to create and version prompts
Step 1: Create a new project in Langtrace and go to the Prompts tab. Click on the "Create Prompt" button to create a new prompt.
Step 2: Paste the Zod schema in the "Prompt" field. You can define the schema for the tool calling in the Zod format. This schema will be automatically converted to JSON schema which is accepted by the OpenAI spec for tool calling.
Step 2: Once you have created a prompt, you can make it available by clicking the "Go Live" button. This will make the prompt available for use in your applications by default when you fetch it using the SDK. When fetched, the schema will be converted to JSON schema and can be directly used for tool calling.
Step 3: Use the prompt in your application by fetching it using the SDK.
```python Python theme={null}
import json
from openai import OpenAI
from langtrace_python_sdk import get_prompt_from_registry
# Initialize OpenAI client
openai = OpenAI(api_key='sk-
')
# Function to make the API call
def make_tool_call():
response = get_prompt_from_registry('
')
function_params = json.loads(response['value'])
completion = openai.chat.completions.create(
model='gpt-3.5-turbo',
messages=[
{
'role': 'system',
'content': 'You are a helpful assistant that can use various tools.'
},
{
'role': 'user',
'content': 'Place an order for 3 units of product 1234'
}
],
functions=[
{
'name': 'order_product',
'description': 'Place an order for a product',
'parameters': function_params
}
]
)
print(completion)
```
```typescript Typescript theme={null}
import { getPromptFromRegistry } from '@langtrase/typescript-sdk'
import OpenAI from 'openai'
// Initialize OpenAI client
const openai = new OpenAI({ apiKey: process.env.OPENAI_API_KEY })
// Function to make the API call
async function makeToolCall (): Promise
{
const response = await getPromptFromRegistry('
')
const functionParams = JSON.parse(response.value)
const completion = await openai.chat.completions.create({
model: 'gpt-3.5-turbo',
messages: [
{
role: 'system',
content: 'You are a helpful assistant that can use various tools.'
},
{
role: 'user',
content: 'Place an order for 3 units of product 1234'
}
],
tool_choice: 'auto',
tools: [
{
type: 'function',
function: {
name: 'order_product',
description: 'Place an order for a product',
parameters: functionParams
}
}
]
})
console.log(JSON.stringify(completion.choices[0]
.message, null, 2))
}
```
Step 4: You can also fetch a specific version of the prompt by passing the version number in the options. And you can get the "Prompt Registry ID" from the Langtrace UI.
That's it! You have successfully created and versioned a zod schema in Langtrace. You can now use this schema in your applications and easily manage and reuse it across your projects.

---

## 

**URL:** https://docs.langtrace.ai/features/playground.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Model Playground
> Langtrace has a model playground where you can interate on your prompts with different models and model settings to see how they perform.
## How to use the model playground
Step 1: Make sure you add your model API keys from Langtrace settings.
We do **NOT** store your API keys. They are stored in your browser's local
storage.
Step 2: Go to the Model Playground tab inside your project. Here you can add your prompts(3), switch roles, and select different models(2) and model settings(5) to see how they perform.
Step 3: Additionally, you can also import entire conversations that were traced and also prompts from prompt registry for iteration and testing.
**How to import traced conversations**
**How to import prompts from prompt registry**

---

## 

**URL:** https://docs.langtrace.ai/hosting/auth.md

> ## Documentation Index
> Fetch the complete documentation index at: https://docs.langtrace.ai/llms.txt
> Use this file to discover all available pages before exploring further.
# Authentication
> Configure various authentication methods for your self-hosted Langtrace setup using NextAuth.js.
## Overview
Langtrace uses [NextAuth.js](https://next-auth.js.org/), a complete open-source authentication solution for Next.js applications. NextAuth.js provides a secure and flexible framework for handling various authentication methods, including OAuth providers and custom credentials.
We support multiple authentication methods to accommodate different organizational needs:
1. [Admin Password Login (custom credentials)](#admin-password-login)
2. [Google OAuth](#google-oauth)
3. [Azure AD OAuth](#azure-ad-oauth)
You can enable one or more of these methods by configuring the appropriate environment variables. Thanks to NextAuth.js, no code changes are required to switch between these authentication options.
## General Configuration
Regardless of the chosen authentication method(s), the following NextAuth.js-related environment variables are required:
```bash theme={null}
NEXTAUTH_SECRET="your_generated_secret_key"
NEXTAUTH_URL="https://your-app-url.com"
```
* `NEXTAUTH_SECRET`: A secure random string used by NextAuth.js to encrypt tokens and sign/encrypt cookies.
* `NEXTAUTH_URL`: The public URL of your application, used by NextAuth.js for callback URLs and links.
Set up a single administrator account
Allow users to log in with their Google accounts
Enable login via Microsoft Azure Active Directory
### Admin Password Login
This method allows a single administrator account to log in using an email and password.
```bash theme={null}
ADMIN_EMAIL="your_admin_email@example.com"
ADMIN_PASSWORD="your_secure_admin_password"
NEXT_PUBLIC_ENABLE_ADMIN_LOGIN="true"
```
Set `NEXT_PUBLIC_ENABLE_ADMIN_LOGIN` to `true` to enable this method.
#### Adding More Users
When using password authentication:
* Log in to the application using the admin account (configured with `ADMIN_EMAIL` and `ADMIN_PASSWORD`).
* Once logged in as admin, you will have access to the user management interface.
* Use this interface to invite additional users to the system.
Only the admin account can invite new users. Regular users cannot create
additional accounts.
This approach allows you to maintain control over user access while still enabling
multiple users to access your Langtrace instance.
### Google OAuth
Allows users to log in using their Google accounts. This method uses OAuth 2.0.
```bash theme={null}
GOOGLE_CLIENT_ID="your_google_client_id"
GOOGLE_CLIENT_SECRET="your_google_client_secret"
```
To obtain these credentials:
1. Go to the [Google Cloud Console](https://console.cloud.google.com/apis/credentials)
2. Create a new project or select an existing one
3. Enable the Google+ API
4. Create OAuth 2.0 credentials (OAuth client ID)
5. Set the authorized redirect URIs. For local development, use:
`http://localhost:3000/api/auth/callback/google`
For production, use your actual domain:
`https://your-app-domain.com/api/auth/callback/google`
6. Note the client ID and client secret
For more information, refer to the official [Google documentation](https://support.google.com/cloud/answer/6158849?hl=en).
When setting up for local development, make sure to add
`http://localhost:3000` to the list of "Authorized JavaScript origins" in your
Google Cloud Console project settings.
### Azure AD OAuth
Enables login via Microsoft Azure Active Directory, suitable for organizations using Microsoft 365 or Azure AD.
```bash theme={null}
AZURE_AD_CLIENT_ID="your_azure_ad_client_id"
AZURE_AD_CLIENT_SECRET="your_azure_ad_client_secret"
AZURE_AD_TENANT_ID="your_azure_ad_tenant_id"
```
To obtain these credentials:
1. Sign in to the Azure portal
2. Register a new application in your Azure AD tenant
3. Note the Application (client) ID and Directory (tenant) ID
4. Create a new client secret
5. Set the redirect URI to `your-app-url/api/auth/callback/azure-ad`
Note the client ID, client secret, and tenant ID
For more information, refer to the official Microsoft documentation.
## Enabling Authentication Methods
To enable a specific login method:
* Set the corresponding environment variables as described above.
* Ensure `NEXTAUTH_SECRET` and `NEXTAUTH_URL` are properly configured.
* Restart your application for the changes to take effect.
The application will automatically enable the login methods for which valid credentials are provided. You can enable multiple methods simultaneously by setting the environment variables for each desired method.
## User Management
* **Admin Account**: Created automatically on first login using the provided `ADMIN_EMAIL` and `ADMIN_PASSWORD`.
* **OAuth Users**: New user accounts are automatically created in the database when users first log in via Google or Azure AD.
## Important Notes
* The system uses a Prisma adapter, which automatically handles user creation and management in the database.
* Google and Azure AD logins allow for automatic account linking if a user with the same email already exists in the database.
## Additional Providers
Need another provider? Langtrace uses [Auth.js](https://authjs.dev/) (formerly
NextAuth.js), which integrates with [many
providers](https://authjs.dev/getting-started/providers). Add a [feature
request on GitHub](https://github.com/Scale3-Labs/langtrace/issues/new) if you
want us to add support for a specific provider.
Langtrace currently supports Admin Password Login, Google OAuth, and Azure AD OAuth out of the box. However, thanks to the flexibility of Auth.js, it's possible to extend this to include many other authentication providers.
If you need support for a provider that's not currently included:
1. Check the [Auth.js providers list](https://authjs.dev/getting-started/providers) to see if your desired provider is supported.
2. If it's supported by Auth.js but not yet implemented in Langtrace, please submit a feature request on our GitHub repository.
3. Our team will review the request and consider adding support for the provider in future updates.
We're always looking to improve Langtrace and make it more versatile for our users' needs. Your feedback and requests help us prioritize development efforts.
