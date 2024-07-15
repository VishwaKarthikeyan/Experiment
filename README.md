# Introduction Overview

This project focuses on automating the extraction and analysis of architecture diagrams to identify and categorize Azure resources and their configurations. The primary output is structured in JSON format, facilitating automation of resource management tasks within Azure environments.

# Tools Used

Utilized GPT-4o model from OpenAI to recognize the architecture diagrams and generate the corresponding JSON output.

# Solution Overview
<p align="center">
  <img src="https://github.com/user-attachments/assets/d443f32a-427e-40d4-9a1c-4a00bf553ac6" alt="image" width="800" height="auto">
</p>




In developing an automated solution for analyzing architecture diagrams, the approach integrates two distinct types of messages: "**system**" and "**user**." These messages are pivotal in facilitating effective interaction and guiding users through the process of extracting and interpreting data from complex diagrams.

## System Role:

Messages assigned the "system" role play a foundational role in providing essential resources and setting the groundwork for effective interaction. These messages are designed to equip users with necessary templates, explanatory content, and visual aids. For example, they include a template JSON structure that exemplifies the expected format of output data, ensuring consistency and accuracy in representations of complex systems. Additionally, these messages offer detailed instructions on interpreting diagrams, highlighting key components such as system components, resource groups, and various services. Visual examples accompanying these instructions enhance comprehension, illustrating concepts like resource existence and network connectivity criteria based on diagrammatic cues. By equipping users with structured information and visual aids, the "system" messages facilitate a clear and systematic approach to automating the extraction and analysis of system architecture data.

## User Role:
Conversely, messages assigned the "user" role simulate the expected interaction and responses from users. These messages guide users through practical steps and directives on effectively navigating and extracting information from system architecture diagrams. For instance, they provide detailed instructions on identifying specific resources, capturing networking details based on visual indicators such as arrow line colors, and ensuring precision in documenting outputs. They outline criteria for accurately determining resource status (existing or new) by interpreting background colors and block fill patterns within the diagrams. Furthermore, the "user" messages present real-world examples and scenarios, illustrating correct and incorrect practices in output generation. By following these instructions, users can streamline the process of generating representations that reflect the intricate configurations of system environments accurately.


# Prompt Engineering

Prompt engineering involves crafting clear and detailed prompts that guide users or automated systems through tasks effectively. This process includes two essential types of prompts: instructions for generating JSON and examples pairing architecture diagrams with corresponding JSON outputs. Instructions outline steps, criteria, and formatting requirements to produce accurate JSON representations from input data. Examples provide visual and textual demonstrations, illustrating how to interpret diagrams and structure JSON outputs according to specified guidelines. This approach ensures tasks are streamlined, validated, and optimized for clarity and accuracy in handling complex data interpretation and output generation tasks.


# Example

<p align="center">
  <img src="https://github.com/user-attachments/assets/24b4f2cd-e4e0-4c35-bf71-f94518cabadf" alt="image" width="800" height="auto">
</p>

<div style="display: flex; justify-content: space-between;">
  <a href="link-to-your-json-file.json">
    <img src="https://github.com/user-attachments/assets/d443f32a-427e-40d4-9a1c-4a00bf553ac6" alt="logo" width="100" height="auto">
  </a>
  <div style="flex: 1; text-align: right;">
    [Link to JSON File](link-to-your-json-file.json)
  </div>
</div>






