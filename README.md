# Desicon Engineering: AI Threat Modelling Workshop Summary

## Introduction
This document summarizes the key points and outcomes of the AI Threat Modelling Workshop conducted for Desicon Engineering, an oil servicing company. The workshop focused on identifying potential threats and vulnerabilities in AI systems, with particular emphasis on the company's use of AWS to host their Oracle EBS (E-Business Suite) and related AI initiatives.

## Attendess
Desicon OracleEBS DevOps team, Product Managers, and the DevSecOps Team.

## Workshop Objectives
1. Understand the unique security challenges posed by AI systems in the context of oil servicing and cloud-hosted ERP
2. Identify potential threats and attack vectors specific to Desicon Engineering's AI implementations and AWS-hosted Oracle EBS
3. Develop a framework for AI threat modeling tailored to Desicon Engineering's infrastructure
4. Create actionable strategies for mitigating AI-related risks within the company's ecosystem

## Methodology
All scenarios were run against the cyber attack killchain, utilising the Mitre Att&ack methods and STRIDE for control gap assessments. Culminating in ide

## Conclusion
A total of 4 high risks and 3 medium risks were found during the threat modelling workshop.

## Key Concepts Covered

### 1. AI-Specific Threat Landscape in Oil Servicing

- Data poisoning attacks on predictive maintenance models
- Model inversion and extraction of sensitive oil field data
- Adversarial examples affecting equipment failure predictions
- Privacy leakage in machine learning models processing client data
- AI safety concerns in automated drilling and production systems

### 2. Threat Modeling Methodologies for Desicon Engineering's AI Systems

- STRIDE model adaptation for AI systems in oil servicing
- Attack trees for AI vulnerabilities in AWS-hosted environments
- DREAD risk assessment for AI threats to Oracle EBS and related systems

### 3. Desicon Engineering's AI System Components and Attack Surfaces

- Training data from oil field sensors and equipment
- Model architecture for predictive maintenance and production optimization
- Inference pipeline integrated with Oracle EBS
- AWS deployment environment
- Human-AI interaction points in drilling and servicing operations

## Workshop Outcomes

### 1. AI Threat Model Framework for Desicon Engineering

Participants developed a structured approach to AI threat modeling specific to the company:
a. System decomposition of AWS-hosted Oracle EBS and AI components
b. Threat identification in the context of oil servicing operations
c. Vulnerability analysis of cloud-hosted AI models
d. Risk assessment considering both AI and traditional ERP threats
e. Mitigation strategy development aligned with AWS best practices

### 2. Common AI Vulnerabilities Identified in Desicon Engineering's Context

- Insufficient sanitization of sensor data from oil fields
- Lack of robustness against adversarial inputs in equipment failure prediction models
- Overreliance on black-box models for critical decision-making in drilling operations
- Inadequate access controls for AI models and Oracle EBS data in AWS
- Insufficient monitoring of AI system behavior across cloud and on-premise components

### 3. Mitigation Strategies

- Implement robust data validation for oil field sensor inputs
- Employ adversarial training techniques for equipment failure prediction models
- Develop interpretable AI models for critical drilling and production decisions
- Implement strong access controls and encryption for AI assets and Oracle EBS in AWS
- Establish continuous monitoring and anomaly detection across the entire AI pipeline

## Action Items

1. Integrate AI threat modeling into existing AWS and Oracle EBS security processes
2. Develop Desicon Engineering-specific AI security guidelines
3. Conduct regular AI security assessments and penetration testing on AWS-hosted systems
4. Invest in AI security training for development, operations, and field teams
5. Establish an AI ethics committee to oversee AI development and deployment in oil servicing operations

## Conclusion

The AI Threat Modelling Workshop provided valuable insights into the unique security challenges posed by AI systems in Desicon Engineering's oil servicing operations and AWS-hosted environment. By adopting a structured approach to threat modeling and implementing the suggested mitigation strategies, Desicon Engineering can significantly enhance the security and reliability of their AI applications and Oracle EBS deployment.

## Next Steps

1. Distribute this summary to all relevant stakeholders in Desicon Engineering
2. Schedule follow-up sessions to deep dive into specific AI security topics relevant to oil servicing
3. Begin implementing the action items identified during the workshop
4. Plan for a follow-up workshop to assess progress and refine strategies
5. Collaborate with AWS and Oracle to ensure alignment with their security best practices

# Threat Modelling Process Summary

```mermaid
  graph TD
    subgraph AWS Cloud
        OracleEBS[Oracle EBS]
        AIModels[AI Models]
        DataStorage[Data Storage]
    end

    subgraph On-Premise
        Sensors[Oil Field Sensors]
        FieldEquipment[Field Equipment]
        OperationsTeam[Operations Team]
    end

    Sensors -->|Data Feed| DataStorage
    FieldEquipment -->|Usage Data| DataStorage
    DataStorage -->|Training Data| AIModels
    AIModels -->|Predictions| OracleEBS
    OracleEBS -->|Business Logic| OperationsTeam
    OperationsTeam -->|Decisions| FieldEquipment

    DataPoisoning[Data Poisoning] -->|Threat| Sensors
    ModelExtraction[Model Extraction] -->|Threat| AIModels
    AdversarialAttacks[Adversarial Attacks] -->|Threat| AIModels
    CloudVulnerabilities[Cloud Vulnerabilities] -->|Threat| OracleEBS
    InsiderThreats[Insider Threats] -->|Threat| OperationsTeam

    style DataPoisoning fill:#f9f,stroke:#333,stroke-width:2px
    style ModelExtraction fill:#f9f,stroke:#333,stroke-width:2px
    style AdversarialAttacks fill:#f9f,stroke:#333,stroke-width:2px
    style CloudVulnerabilities fill:#f9f,stroke:#333,stroke-width:2px
    style InsiderThreats fill:#f9f,stroke:#333,stroke-width:2px
