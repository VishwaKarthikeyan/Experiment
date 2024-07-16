# Introduction

This project focuses on automating the extraction and analysis of architecture diagrams to identify and categorize Azure resources and their configurations. The primary output is structured in JSON format, facilitating automation of resource management tasks within Azure environments.

# Tools Used

Utilized GPT-4o model from OpenAI to recognize the architecture diagrams and generate the corresponding JSON output.

# Solution Overview
<p align="center">
  <img src="https://github.com/user-attachments/assets/d443f32a-427e-40d4-9a1c-4a00bf553ac6" alt="image" width="800" height="auto">
</p>




In developing an automated solution for analyzing architecture diagrams, the approach integrates two distinct types of messages: "**system**" and "**user**." These messages are pivotal in facilitating effective interaction and guiding users through the process of extracting and interpreting data from complex diagrams.

## System Role:

Messages labeled "system" provide essential templates, explanations, and visual aids. They include a JSON template for consistent system data representation and clear instructions on diagram interpretation, highlighting key components like system elements, resource groups, and services. Visual examples illustrate concepts such as resource existence and network connectivity. These messages ensure a systematic approach to automating system architecture data analysis.

## User Role:
Messages labeled "user" guide practical steps for navigating system architecture diagrams. They detail how to identify resources, interpret networking details from visual cues, and accurately document outputs. They clarify criteria for determining resource status within diagrams. Real-world examples demonstrate correct and incorrect practices in output generation, ensuring accurate representations of system configurations.


# Prompt Engineering

Prompt engineering involves crafting clear, concise prompts to guide users or automated systems effectively. This includes instructions for generating JSON and examples pairing diagrams with corresponding JSON outputs. Instructions outline steps, criteria, and formatting requirements for accurate data representation. Examples provide visual and textual demonstrations, ensuring clarity and accuracy in complex data interpretation and output generation tasks.


# Example

<p align="center">
  <img src="https://github.com/user-attachments/assets/24b4f2cd-e4e0-4c35-bf71-f94518cabadf" alt="image" width="800" height="auto">
</p>

![image](https://github.com/user-attachments/assets/c940a80b-faa7-49c3-aa59-8f2ab1d418a3)















